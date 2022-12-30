# bHyve-AIO
bHyve All-in-One will (eventually) turn a fresh installation of FreeBSD 13+ into a standalone hypervisor that can be maintained within a corporate environment.

Platform: 
+ FreeBSD 13 and onwards
+ ZFS
+ bHyve

Automation:
+ Have a web interface for virtual machine management (Apache + PHP)
+ Have a way to initialize ZFS storages
+ Have a way to schedule and manage ZFS snapshots (cron ?)
+ Have a way to backup virtual machines (rsync)
+ Have a way to move virtual machines to another host (rsync)
+ Have a way to monitor performance (PHP)
+ Have a temporary (in-memory) and a persistent database (MariaDb)
+ Have a per user task queue with an API interface (PHP)
+ Have a way to start/stop FreeBSD services (ssh, rsync)
+ Have a way to update OS and packages 
  (save state of all virtual machines, shutdown all non essential services, update, reboot host)
+ Have OS templates
+ Use FreeBSD local users across all functionality

Alternatives considered:
+ CBSD - Not moving fast enough for me
+ bhyve-webadmin - lacks major features / not open source

PHP and not Python ?
+ Less code/dependencies to maintain

Target user groups:
+ DevOps running DevTest environments
+ No noobs

Am I missing something ?
+ Let me know - have an issue opened
