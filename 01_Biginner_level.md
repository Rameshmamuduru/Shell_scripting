# File Organizer Script
Automatically sort files in a directory into folders based on file type (e.g., .jpg → Images, .pdf → Documents).
Skills: if, case, mv, mkdir.

```
#!/bin/bash

folder_path=/tmp

mkdir -p $folder_path/{Images,Documents,Scripts,Logs,Others}

for file in $folder_path/*; do

        # check if it is a file
        if [ -f "$file" ]; then

                case "$file" in
                        *.jpg|*.png|*.jpeg)
                                mv "$file" $folder_path/Images
                                ;;
                        *.pdf|*.txt)
                                mv "$file" $folder_path/Documents
                                ;;
                        *.sh)
                                mv "$file" $folder_path/Scripts
                                ;;
                        *.log)
                                mv "$file" $folder_path/Logs
                                ;;
                        *)
                                mv "$file" $folder_path/Others
                                ;;
                esac
        fi
done
```

# Disk and CPU Usage Monitor
Check disk space and alert if usage exceeds a threshold.
Skills: df, awk, conditional checks.

top 
```
root@dev:/home/ubuntu# top -bn1 | grep  Cpu
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st 
root@dev:/home/ubuntu#

| Value   | Meaning                                         |
| ------- | ----------------------------------------------- |
| 5.5 us  | CPU used by **user processes**                  |
| 1.2 sy  | CPU used by **system/kernel processes**         |
| 0.0 ni  | CPU used by **nice processes** (lower priority) |
| 92.9 id | CPU **idle** (not doing anything)               |
| 0.2 wa  | CPU waiting for **I/O** (disk/network)          |
| 0.0 hi  | CPU handling **hardware interrupts**            |
| 0.2 si  | CPU handling **software interrupts**            |
| 0.0 st  | CPU stolen by **virtualization**                |
```

# Backup Script
Compress and back up a folder to a specified location with a timestamp.
Skills: tar, gzip, date formatting.

# Simple Calculator
Perform basic arithmetic operations from the terminal.
Skills: read, arithmetic expansion $(( )).
