# Conditional Statements
```
#!/bin/bash
disk_free=$(df / | tail -1 | awk '{print $4}')
if [ $disk_free -lt 100000 ]; then
  echo "Warning: Low disk space!"
else
  echo "Disk space is OK."
fi
```
# Loop throgh files
```
#!/bin/bash
for file in /var/log/*.log; do
  echo "Processing $file"
  echo "Lines containing ERROR: $(grep -c ERROR $file)"
done
```

