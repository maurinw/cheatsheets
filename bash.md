# Bash

## Basic Commands
```bash
pwd                 # Print current directory
ls                  # List files in directory
ls -la              # List all files (including hidden) with details
cd <directory>      # Change directory
cd ..               # Move up one directory
mkdir <dir>         # Create a new directory
rmdir <dir>         # Remove an empty directory
rm <file>           # Delete a file
rm -r <dir>         # Remove a directory and its contents
mv <source> <dest>  # Move/rename a file or directory
cp <source> <dest>  # Copy a file or directory
touch <file>        # Create a new empty file
```

## File Viewing
```bash
cat <file>         # Display file contents
less <file>        # View file contents page by page
head <file>        # Show first 10 lines of a file
tail <file>        # Show last 10 lines of a file
tail -f <file>     # Continuously monitor a file (e.g., logs)
```

## File Permissions
```bash
chmod 755 <file>    # Change file permissions (rwx for owner, rx for others)
chmod +x <file>     # Make a file executable
chown user:group <file>  # Change file owner and group
```

## Process Management
```bash
ps aux              # List all running processes
top                 # Monitor system resources in real time
kill <PID>          # Terminate a process by PID
kill -9 <PID>       # Force kill a process
pkill <name>        # Kill a process by name
bg                  # Resume a stopped process in the background
fg                  # Bring background process to foreground
jobs                # List background jobs
```

## Searching and Finding Files
```bash
find /path -name "file.txt"   # Search for a file by name
find . -type f -size +10M     # Find files larger than 10MB
grep "pattern" <file>         # Search for a pattern in a file
grep -r "pattern" <dir>       # Search recursively in directory
grep -i "pattern" <file>      # Case-insensitive search
grep -v "pattern" <file>      # Exclude lines matching pattern
```

## Redirection and Piping
```bash
command > file     # Redirect output to a file (overwrite)
command >> file    # Append output to a file
command 2> file    # Redirect error output to a file
command 2>&1       # Redirect error output to standard output
command | another  # Pipe output of one command into another
```

## Environment Variables
```bash
echo $HOME        # Display value of HOME variable
export VAR=value  # Set an environment variable
unset VAR         # Remove an environment variable
env               # List all environment variables
```

## File Compression
```bash
tar -cvf archive.tar <dir>  # Create a tar archive
tar -xvf archive.tar        # Extract a tar archive
tar -czvf archive.tar.gz <dir>  # Create a gzipped tar archive
tar -xzvf archive.tar.gz    # Extract a gzipped tar archive
zip -r archive.zip <dir>    # Create a zip archive
unzip archive.zip           # Extract a zip archive
```

## Networking
```bash
ping google.com             # Check network connectivity
curl -I example.com         # Fetch HTTP headers
wget <url>                  # Download a file from a URL
netstat -tulnp              # List open ports
```

## Disk Usage
```bash
df -h                      # Show available disk space
du -sh <dir>               # Show disk usage of a directory
du -ah <dir> | sort -rh    # Show largest files in a directory
```

## User Management
```bash
whoami                     # Show current user
who                        # Show logged-in users
sudo command               # Run command as superuser
su - user                  # Switch user
passwd                     # Change password
```

## Package Management
### Debian-based (Ubuntu, Debian)
```bash
sudo apt update            # Update package list
sudo apt upgrade           # Upgrade installed packages
sudo apt install <package> # Install a package
sudo apt remove <package>  # Remove a package
sudo apt search <package>  # Search for a package
```
### RedHat-based (CentOS, Fedora)
```bash
sudo yum update            # Update system packages
sudo yum install <package> # Install a package
sudo yum remove <package>  # Remove a package
```

## Bash Scripting Basics
```bash
#!/bin/bash

echo "Hello, World!"  # Print text

VAR="Bash Scripting"   # Define a variable
echo "I am learning $VAR"

# If statement
if [ -f "file.txt" ]; then
    echo "File exists"
else
    echo "File does not exist"
fi

# For loop
for i in {1..5}; do
    echo "Loop iteration $i"
done

# While loop
count=1
while [ $count -le 5 ]; do
    echo "Count is $count"
    ((count++))
done

# Function
function greet() {
    echo "Hello, $1!"
}
greet "User"
```

## Job Scheduling with Cron
```bash
crontab -e                 # Edit cron jobs
crontab -l                 # List cron jobs
```
### Cron job format:
```
# ┌───────────── minute (0 - 59)
# │ ┌──────────── hour (0 - 23)
# │ │ ┌────────── day of month (1 - 31)
# │ │ │ ┌──────── month (1 - 12)
# │ │ │ │ ┌────── day of week (0 - 6) (Sunday=0)
# │ │ │ │ │
# * * * * * command to execute
```
Example:
```bash
0 6 * * * /path/to/script.sh  # Run script daily at 6 AM
```

## SSH (Remote Access)
```bash
ssh user@host               # Connect to remote host
scp file user@host:/path/   # Copy file to remote host
rsync -av source/ dest/     # Sync directories
```