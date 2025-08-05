# Simple-System-Monitor-Bash-Script
A simple Bash script for general system monitoring that I wrote on a car trip.
Note: ``net-tools`` is required to run this script.

The dissection of the script is as follows.
```
watch -c -t -n 2
echo "@`hostname` | `date`" 
echo "\033[30;47m WhoMon--------------------------------------------------------\033[0m" & who ;
echo "\033[30;47m PortMon--------------------------------------------------------\033[0m" & sudo netstat -tulpn | grep LISTEN ;
echo "\033[30;47m DiskMon--------------------------------------------------------\033[0m" & df -h ;
echo "\033[30;47m FileMon--------------------------------------------------------\033[0m" & sudo find /etc /var /bin /boot /home -type f -mmin -0.3 | tail -n 7 ;
echo "\033[30;47m TopMon--------------------------------------------------------\033[0m" & top | head -n 14 | tail -n 13 ;
```
Demo On A Kubuntu 20.04.05 VM.
https://github.com/user-attachments/assets/c2c0b4eb-ddce-486b-bc0b-96f175a40af3


