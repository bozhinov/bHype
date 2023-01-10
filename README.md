# bHype
# bHype should (eventually) turn a fresh installation of FreeBSD 13+ into a standalone virtual machine host that can be maintained within a corporate environment.

Platform: 
+ FreeBSD 13 and onwards
+ ZFS
+ bHyve

Automation:
+ Have a web interface for virtual machine management (nginx + PHP)
+ Have OS templates
+ Include noVNC (regardless of being MPL 2.0)
+ Use FreeBSD local users across all functionalities
+ Have a way to initialize ZFS storages
+ Have a way to schedule and manage ZFS snapshots (cron ?)
+ Have a way to backup virtual machines / including to a Windows host (rsync)
+ Have a way to move virtual machines to another host (rsync)
+ Have a way to clone a virtual machine (iohyve)
+ Have a way to monitor/record virtual machines performance (native tools)
+ Have a way to monitor over all host resource utilization 
+ Have a temporary (in-memory) and a persistent database (MariaDb)
+ Have a per user task queue with an API interface (PHP)
+ Have a way to start/stop FreeBSD services (ssh, rsync)
+ Popup notifications in case of pkg audit vulnerabilities discovered (cron)
+ Popup notifications in case of OS patches available (cron)
+ Have a process to update OS and packages 
  (save state of all virtual machines, shutdown all non essential services, update, reboot host)
+ SNMP alerts (if there is time)

Alternatives considered:
+ CBSD / ClonOS - Not moving fast enough for me
+ bhyve-webadmin - lacks major features / not open source
+ vm-bhyve - will probably reverse some of its functionalities and reuse them
+ iohyve - will probably reverse some of its functionalities, especially the cloning one

All PHP and not Python?
+ Less code/dependencies to maintain

Target user groups:
+ DevOps running DevTest environments
+ No noobs

Will it be ever suitable for production ?
+ Don't think so. 
1) Troubleshooting and maintenance - The platform is not popular amongst IT personnel
2) Maturity - The code has been around for a while but does not seem to be thoroughly tested.
3) Lacks features like live migration, video acceleration, direct guest communication

Am I missing something ?
+ Let me know - have an issue opened
