# Linux Scavenger Hunt
<h2> Flag 1 </h2>
<b>Task: </b>
Finding this flag is imperative to moving on quickly, as it contains the passwords from users before they were hacked. Luckily, it doesn't have a great hiding spot.
<br />
<br />
<b>Action: </b> To locate the first flag, I executed the <b>ls -alt</b> command, listing all files and directories (including hidden ones) sorted by their most recent modifications. This approach allowed me to uncover poorly hidden files, such as a plaintext password list, which ultimately contained the flag. <br />
<p align="center">
<img src="https://i.imgur.com/7H7XiFd.png" height="80%" width="90%" alt=""/>

<h2> Flag 2 </h2>
<b>Task: </b>
A famous hacker had created a user on the system a year ago. Find this user, crack their password, and log in to their account.
<br />
<br />
<b>Action: </b> After uncovering the exposed user password file in the first task (flag_1), I proceeded to analyze the shadow file, which stores password hashes. This file contained entries for both the current user and the infamous hacker referenced in flag_2, providing an opportunity for password-cracking attempts to escalate access. Using <b>john</b>, I successfully cracked the hacker’s password and leveraged the <b>su</b> command to log into their compromised account. This privilege escalation granted access to flag_2, typically located in the user’s home directory or related files. <br />
<p align="center">
<img src="https://i.imgur.com/yKkUMtu.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/NcXDHPD.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/5tavKcm.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/cL6GsEW.png" height="80%" width="90%" alt=""/>

<h2> Flag 3 </h2>
<b>Task: </b>
Find a log file related to the hacker's name and a zip file with additional info. Use a compound command to figure out the unique count of IP addresses in this log file. That number is a password.
<br />
<br />
<b>Action: </b> Now logged in as the infamous hacker 'mitnick' through privilege escalation, I began the hunt for flag_3. First, I audited the <b>/var/log/</b> directory for logs associated with this user using commands like <b>ls -alt</b>. To unlock the zip file, I crafted a compound command to parse the log file, extract all IP addresses, filter for unique entries, and count them—using this total as the password. Next, I searched mitnick’s directories for relevant zip files using the <b>find</b> command. Once located, I used <b>unzip</b> to extract the contents, which could contain logs or additional clues leading to flag_3. <br />
<p align="center">
<img src="https://i.imgur.com/X8Nwb0K.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/cuFQtXU.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/h0dMjs1.png" height="80%" width="90%" alt=""/>

<h2> Flag 4 </h2>
<b>Task: </b>
Find a directory with a list of hackers. Look for a file that has read permissions for the owner, no permissions for groups, and executable only for everyone else.
<br />
<br />
<b>Action: </b> To locate this flag, I used the <b>ls -alt</b> command to navigate through all directories belonging to the user, listing files and subdirectories in detail. This allowed me to identify the directory containing the names of all hackers and pinpoint files with read permissions for the owner and executable permissions for everyone else. Once identified, I used the <b>cat</b> command to extract the word contained within the 'stallman' file and used it as the password to switch to the 'stallman' user. <br />
<p align="center">
<img src="https://i.imgur.com/x4rcMui.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/rOMQ385.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/MPBrx6J.png" height="80%" width="90%" alt=""/>

<h2> Flag 5 </h2>
<b>Task: </b>
This user is writing a Bash script, except it isn't quite working yet. Find it, debug it, and run it.
<br />
<br />
<b>Action: </b> To locate the script file, I used the <b>find</b> command to search through the current user's directories. Once identified, I debugged the script file using <b>nano</b>. Additionally, I executed the <b>chmod +x</b> command to grant executable permissions, enabling me to run the script successfully. <br />
<p align="center">
<img src="https://i.imgur.com/KAKfkgv.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/aAW67R2.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/nLqEo22.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/CgeZNWv.png" height="80%" width="90%" alt=""/>

<h2> Flag 6 </h2>
<b>Task: </b>
Inspect this user's custom aliases and run the suspicious one for the proper flag.
<br />
<br />
<b>Action: </b> To find this flag, I switched to the 'sysadmin' user using the password obtained along with flag_5 after running the script file. I then inspected the aliases using the <b>alias</b> command and executed any suspicious alias, successfully generating the flag. <br />
<p align="center">
<img src="https://i.imgur.com/OvQV71l.png" height="80%" width="90%" alt=""/>

<h2> Flag 7 </h2>
<b>Task: </b>
Find an exploit to gain a root shell. Log in as the root user.
<br />
<br />
<b>Action: </b> To find an exploit for gaining root access, I first checked the user's sudo permissions using the <b>sudo -l</b> command. This helped identify potential privileges or misconfigurations that could be exploited for privilege escalation. Upon discovering that I could run the <b>sudo less</b> command, I leveraged it to escalate privileges. I then used the <b>touch</b> command to create a file that allowed me to execute commands or manipulate the system, ultimately enabling me to log in as the root user. <br />
<p align="center">
<img src="https://i.imgur.com/eX9RzmI.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/YOzxaqq.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/pQJP8Cs.png" height="80%" width="90%" alt=""/>
