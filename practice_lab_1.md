# Bash-Scripting

## Hello World Script
```
#!/bin/bash
# Prints system info
echo "Hello, $USER!"
echo "Current date and time: $(date)"
echo "Current working directory: $(pwd)"
```

## Variables and User inputs
```
#!/bin/bash
echo "Enter your name:"
read name
echo "Welcome, $name! Today is $(date)"
```

## Conditional Statement
```
#!/bin/bash
disk_free=$(df / | tail -1 | awk '{print $4}')
if [ $disk_free -lt 100000 ]; then
  echo "Warning: Low disk space!"
else
  echo "Disk space is OK."
fi
```
