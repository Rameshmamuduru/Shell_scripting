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

# Disk Usage Monitor
Check disk space and alert if usage exceeds a threshold.
Skills: df, awk, conditional checks.

# Backup Script
Compress and back up a folder to a specified location with a timestamp.
Skills: tar, gzip, date formatting.

# Simple Calculator
Perform basic arithmetic operations from the terminal.
Skills: read, arithmetic expansion $(( )).
