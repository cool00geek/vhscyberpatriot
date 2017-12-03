# Linux Scoring Engine

#### An alternative cybersecurity scoring engine for Linux platforms!

## Introduction
 This is a scoring engine for Linux designed with CyberPatriot in mind, but theoretically can be adapted and used for many cyberdefense competitions and other scenarios. Development of this engine was spearheaded by Vinay Venkat.

## Features
- GUI wizard for vulnerability creation
    - Monitoring files for changes
    - Monitoring command output
    - Installed programs
    - User vulnerabilities
- Automatically generates compiled `deb`, `rpm`, or `sh` to be installed on the target virtual machine
- Automatic score upload to an Azure database for tracking with software such as [CyberTiger Scoreboard](https://github.com/billwi/CyberTigerScoreboard).
    - This scoring engine and CyberTiger Scoreboard were designed in tandem to work together as a cohesive whole, so any data uploaded to an Azure database by the engine can be automatically parsed and interpreted by CyberTiger Scoreboard.


## System Requirements

### GUI Vulnerability Creation Tool
- Any recent version of macOS or Linux
- Java 8
- Ruby devel for `fpm`
- More specific software requirements have not been determined at this time
- Hardware requirements have not been determined at this time, but the GUI should run on any reasonably powered hardware (i.e. hardware requirements won't be an issue for anyone planning to run this software)

### Instructions for setting up the GUI
Run the following script as root
```shell
apt-get update
apt-get install default-jre
apt-get install ruby-dev
gem install fpm
```

### Compiled Vulnerability Checking Sofware
- Ubuntu 16.04 LTS or higher for database functionality
- Ubuntu 14.04 LTS or greater for all other features
- Requirements for other Linux distributions have not been determined at this time.

## Instructions for Sending Scores to an Azure Database

1. Run the below shell script
2. Install `default-jre`, `ruby-dev`, and `fpm` through gem.

[Shell Script to with superuser privileges (e.g. sudo) for Ubuntu Environments](https://gist.github.com/billwi/fc7bdbec214c9a964af69498c08e48ec)

### Script Contents:
```shell
#!/bin/bash
apt-get install curl
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
curl https://packages.microsoft.com/config/ubuntu/$(lsb_release -r -s)/prod.list > /etc/apt/sources.list.d/mssql.list
apt-get update
apt-get -y install msodbcsql mssql-tools unixodbc-dev
apt-get -y install python-pip
pip install pyodbc==3.1.1
```
## People Involved/Contact Information

### Vinay Venkat

Chief Designer/Programmer for The Linux Scoring Engine

714-406-0019

<a href="mailto:cool00geek@yahoo.com?subject=Linux Scoring Engine&body=This email is regarding the Linux Scoring Engine, and I would like more information about it">cool00geek@yahoo.com</a>


### Irvin Lemus

Advisor/CyberPatriot Regional Coordinator

<a href="mailto:irvin.lemus@wastc.org?subject=Linux Scoring Engine&body=This email is regarding the Linux Scoring Engine, and I would like more information about it">irvin.lemus@wastc.org</a>
