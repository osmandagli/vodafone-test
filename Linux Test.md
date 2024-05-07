# 2.nd 
~~~
if ! test -d /backup/logs ; then
  mkdir -p /backup/logs
fi

find /var/log -name *.log | xargs -I % cp % /backup/logs
~~~
