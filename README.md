# hosts_ad_blocker
A Bash script designed to download lists of ad / tracker servers to block with the hosts file.
It uses the default Adaway hosts file to block ads and trackers (for the basic option), and then downloads two variations of
Steven Black's hosts file for filtering of sites known to spread misinformation as well as gambling (moderate option) and
an extreme option that blocks pornography and social media in addition to what is mentioned above.

On first run, the script will create a folder in ~/.config that stores hosts files and a file that tells the script that an initial 
run had been complete to finalize the backup process. The different options are then available to users once definitions
are finished downloading.

This does modify the hosts file on a Linux system and creates two backups for redundancy. This redundancy
also protects against errors in code, as well as user error. A transcript of the '--help' option is available below.

INSTALLATION: copy the script to any path defined in $PATH. If in a system path (i.e. /usr/local/bin, /usr/bin, etc.) then
ensure that permissions are set through 'chmod 755 /path/to/script'.

USAGE: hosts_switch_generate [ options ... ]
where options include:

-u or --update    Update hosts file lists

-h or --basic     Use the default list provided by Adaway

-m or --moderate  Use the 'Unified Hosts + Fakenews + Gambling' StevenBlack
                  hosts list

-e or --extreme   Use the Unified Hosts + fakenews + gambling + porn + social
                  StevenBlack hosts list

If you, for whatever reason deleted the configuration folder
while already having a generated hosts file, you may have overwritten your
original hosts file. Fortunately this utility keeps a hidden backup
in your home directory as '.hosts' upon the first run.
Run this utility with '-R' or '--recover' to restore your stock hosts
in case something like this happens.
