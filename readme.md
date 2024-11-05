
Linux Project

The purpose of this project is to develop a script that logs the system’s uptime along with the
current timestamp. The log file is stored in a directory, and the logging is automated using the
cron job scheduler. Additionally, this project addresses permission management issues to
allow both privileged and non-privileged logging depending on the system requirements. The
report documents the steps undertaken to create, execute, and automate the script, alongside
solutions to common challenges such as file permissions and automation.

Requirements:
Redhat Linux Enterprises
httpd package


Steps:

1. creating a script
---- nano uptime_logger.sh
a. add the following script to capture and log the system's unique
---- uptime_info=$(uptime -p)
current time=$(date)
echo "$current_time - $uptime_info" >>/var/log/uptime_log.txt
echo "uptime logged to /var/log/uptime_log.txt"
b. save and exit the file (ctrl + x,THEN y, THEN eNTER)
2. Make the script executable
chmod +x uptime _logger.sh
3. run the script
./uptime_logger.sh
4. check the log file
cat /var/log/uptime_log.txt
5. automate the logging with cron
a. crontab -e
b.0** **
/path/to/uptime_logger.sh
save the crontab (ctrl + ×, THEN y,THEN eNTER)
6. verify cron tab
cat /var/log/uptime_log.txt


Now Save and run it:
1. run the script as root
sudo./uptime_logger.sh
2. to view the log file
sudo cat /var/log/uptime_log.txt
---- modify the script to save the log file

uptime _info=$(uptime -p)
current _time=$(date)
echo "$current_time - $uptime_info" >> /var/log/uptime_log.txt
echo "uptime logged to /var/log/uptime_log.txt"
---- run the script without needing sudo
./uptime_logger.sh
----to view the log file
cat ~/uptime_log.txt
to show the project run these commands
sudo./uptime_logger.sh ------run the script
sudo cat /var/log/uptime_log.txt------to view the log file


