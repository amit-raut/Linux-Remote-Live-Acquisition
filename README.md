# Linux Remote Live Acquisition
Remotely Acquire Volatile Data on Linux Based System

## Summary
Send commands to the target Linux system using secure copy SCP and get back the output of the commands to the examiner system

## Requirement
The preferred way for sending and receiving the files in this is via key based authentication. To set up key bidirectional key based secure copy transfers please follow instructions provided at http://www.tecmint.com/ssh-passwordless-login-using-ssh-keygen-in-5-easy-steps/

## Working

* Executing the python script will look for the command file with extension .livedata in /tmp/ folder.

* The examiner system can send the command file to the target system using secure copy (SCP) to folder /tmp/

* Once the python script finds the command file it starts executing the commands and dump output to /tmp/LiveAcquisition/<datetimedatetime.now()> folder.

* SHA256 hash for each command output is calculated and saved in the same folder with .sha256 extension

* Complete folder is then archived in gztar format and saved at /tmp/ with name 'liveAcquisitionData.tar.gz'

* The gztar archive is then sent back to the examiner system over secure copy (SCP)

## Usage
```
Usage: linuxRemoteLiveAcquition -u [remote system user] -i [examiner system IP address]
```


Thank you, :-)
