# mkmirror - The complete all-in-one multi-os mirror system
It is a comprehensive Multi-OS Mirror System that sets up dedicated docker containers to act as a local mirror for each configured OS version. This greatly simplifioes standing up local mirrors when you need to, and with a reverse proxy you can keep the high traffic ones onsite and use a public mirror for the rest

# Currently Supports
* Ubuntu: 16.04, 18.04, 20.04, 22.04, 24.04, 25.04
* Debian: 5, 6, 7, 8, 9, 10, 11, 12
* CentOS: 5, 6, 7, 8, 9
* CentOS Stream: 8, 9, 10
* AlmaLinux: 8, 9
* Rocky Linux: 8, 9

# Multiple Access Methods for Each Mirror
* HTTP access for standard apt/yum client configuration
* HTTPS access for secure connections
* FTP access for legacy compatibility
* rsync access via daemon & ssh mode

# Automated Resource Management
* Each OS gets its own dedicated Docker container
* Repositories sync automatically at scheduled times

# Management Tools
* Complete management script for controlling each specific os version
* Easy commands to start/stop specific distributions
* Monitor status, view logs, and trigger syncs

# Port Allocation System
To keep things organized, each OS version gets its own set of ports:

* Ubuntu versions: 1000-1999 range
* Debian versions: 2000-2999 range
* CentOS versions: 3000-3999 range
* CentOS Stream: 4000-4999 range
* AlmaLinux: 5000-5999 range
* Rocky Linux: 6000-6999 range

For each distribution version, these ports are allocated:

* HTTP: 8000 + offset (e.g., 8001, 8002, etc.)
* HTTPS: 8100 + offset (e.g., 8101, 8102, etc.)
* FTP: 2100 + offset (e.g., 2101, 2102, etc.)
* SSH (for rsync): 2200 + offset (e.g., 2201, 2202, etc.)
* rsync daemon: 8700 + offset (e.g., 8701, 8702, etc.)
