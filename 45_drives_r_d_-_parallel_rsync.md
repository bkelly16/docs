# Parallel Rsync



*  ls -1 $LOCAL_DIR | xargs -I {} -P 5 -n 1 rsync -avh --progress $LOCAL_DIR/{} $RECV_DIR

*  -P sets number of parallel threads




