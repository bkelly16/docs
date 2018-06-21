# Nagios Setup

 1.  Set up monitoring nagios server as per any guide
 2.  Set up NRPE on each remote host as per a combo of

      * https://assets.nagios.com/downloads/nagioscore/docs/nrpe/NRPE.pdf
      * http://www.thegeekstuff.com/2010/12/enable-nrpe-command-arguments/
 3.  Main things to remember

      * Make sure nagios owns plugins folder (/usr/lib64/nagios/plugins/)
      * Use sudo on remote host command spec
      * compile nrpe from source make sure to use the "./configure --enable-command-args"
      * /usr/local/nagios/etc/nrpe.cfg   ;   dont_blame_nrpe=1
    

