# Real Time Monitoring

Ceph can send performance metrics to a promtehues endpoint

Prometheus stores in a time series database

Grafana queires and displays Prometheus data 

**The current verison of Ceph Prometheus Plugin cannot display latencies properly**

Ceph exports latency values using a floating point value for the average count and sum. The average count is teh number of operations within this range and the sum is total latency in seconds. To get the real latency per operation you need to divde avgcount by the sum.

The ceph-prometheus plugin currently only exports the sum. Therefore not an accurate measur eof latency per operation.  

More info on how ceph reports its performance data. [ Ceph Performance Counters](https///access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/administration_guide/performance_counters#osd-rw-ops-table)

More info on Ceph-Prometheus limiations. [ CephPrometheus Limiations](http://docs.ceph.com/docs/mimic/mgr/prometheus/#notes)

**Possible solutions are exploring Zabbix, Influx, or telegraf**

## Install Prometheus Server

Install to /opt

    wget https://github.com/prometheus/prometheus/releases/download/v2.2.1/prometheus-2.2.1.linux-amd64.tar.gz
    tar -zxvf prometheus-2.2.1.linux-amd64.tar.gz -C /opt/
    ln -s prometheus-2.2.1.linux-amd64/ prometheus
    
Create systemd script

    vim /usr/lib/systemd/system/prometheus.service

    [Unit]
    Description=Prometheus Server
    Documentation=https://prometheus.io/docs/introduction/overview/
    After=network-online.target
    [Service]
    User=root
    Restart=on-failure
    ExecStart=/opt/prometheus/prometheus --config.file=/opt/prometheus/prometheus.yml                          
    [Install]
    WantedBy=multi-user.target

Start Service, and verify you can reach Prometheus webUI. http://HOST:9090

    systemctl daemon-reload
    systemctl start prometheus


## Install Grafana Server

Install Grafana & Dependancies using a rpm. Get the most up to date rpm from here: http://docs.grafana.org/installation/rpm/#on-centos-fedora-redhat

    yum install initscripts fontconfig https://s3-us-west-2.amazonaws.com/grafana-releases/release/grafana-5.0.1-1.x86_64.rpm
    systemctl daemon-reload
    systemctl enable grafana-server

Verify you can reach grafana webUI. http://HOST:3000
    
## Install node_exporter on Each Node

Download and run the node_epxorter install script on each node you want to monitor

    wget http://images.45drives.com/ceph/install-node_exporter.sh
    sh install-node_exporter.sh

Verify node_exporter is working by pointing your browser to http://HOST:9100/metrics

## Enable Prometheus Plugin on Ceph Cluster

Enable module from a node in the ceph cluster

    ceph mgr module enable prometheus
    ceph mgr module ls 

Verify you can reach the metrics page. http://HOST:9283/metrics
Note that although all mgr nodes can host this, only the active mgr at the time is reachable.

## Configure Prometheus Scrape Config

Put the following in the "prometheus.yml" file

    global:
    scrape_interval:     15s
    evaluation_interval: 15s
    scrape_configs:
   - job_name: 'node'
     file_sd_configs:
       - files:
         - node_targets.yml
   - job_name: 'ceph'
     honor_labels: true
     file_sd_configs:
       - files:
         - ceph_targets.yml

Create node_targets.yml. 
    
    Sample file is here http://images.45drives.com/ceph/node_targets.yml

Create ceph_targets.yml

    Sample file is here http://images.45drives.com/ceph/ceph_targets.yml

Restart Prometheus service

    systemctl restart prometheus

Verify that prometheus can query ceph/node statistics





