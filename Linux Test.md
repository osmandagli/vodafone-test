# Backup Log Files
~~~
if ! test -d /backup/logs ; then
  mkdir -p /backup/logs
fi

find /var/log -name *.log | xargs -I % cp % /backup/logs
~~~

# System Report

~~~
date | awk '{print "Time is",$4,$5;print "Date is",$3,$2,$7}' > system-report.txt
uptime -p | awk '{print "System is",$0}' >> system-report.txt
free -h | awk 'NR==2 {print "Used memory is",$3}' >> system-report.txt
~~~
