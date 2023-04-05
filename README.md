# bHype
bHype should (eventually) turn a fresh installation of FreeBSD 13.2 (or maybe even 14) into a standalone virtual machine host that can be maintained within a corporate environment.

Platform: 
+ FreeBSD 13.2 and onwards
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
+ Have a way to re-register virtual machines with another host
+ Have a way to clone a virtual machine
+ Have a way to start VM upon host boot (persistent VMs)
+ Add an option for VirtIO shares
+ Have Bridged (Public), NAT-ed and Private types of network switches predefined
+ Have a DHCP service (dhcp-php preferably and dnsmasq optionally)
+ Have a service to monitor/record virtual machines performance (native tools)
+ Have a service to monitor over all host resource utilization 
+ Have a temporary (in-memory) and a persistent database (MariaDb)
+ Have a per user task queue with an API interface (PHP)
+ Have a way to start/stop FreeBSD services (ssh, rsync)
+ Have jail templates (ClonOS inspired)
+ Be able to run post-jail-deployment scripts (turn into a container)
+ a.k.a Pot (EuroBSDcon 2022 inspired)

Hardware:
+ CPU: AMD Zen based (2019+)
+ or
+ CPU: Intel with EPT & VT-x (2011+)

+ Notes
+ AMD RVI CPUs are supported by bHyve
+ AMD-Vi and Intel VT-d for the passthrough if you know what's good for you
+ Intel VT-c does not seem to be supported by bHyve

+ GPU: (TBD)
+ Notes
+ Intel GVT-d reportedly works but supported on CPU gens 5 to 10 only
+ All Intel, AMD and Nvidia adapters passthrough work (reportedly)
+ No weird shit like "eGPU connected through a Thunderbolt port"

+ NIC:
+ FreeBSD offers LAGG and I advise you use it if you have multiple NICs

+ STORAGE:
+ The more the merrier

Security:
+ Popup notifications in case of pkg audit vulnerabilities discovered (cron)
+ Popup notifications in case of OS patches available (cron)
+ Have a process to update OS and packages (poudriere)
  (save state of all virtual machines, shutdown all non essential services, update, reboot host)
+ SNMP alerts (if there is time)
+ Make sure OSSEC works in the final distribution.

Build system:
+ Seems everyone went for poudriere
+ I like pfsense's one for now
+ NanoBSD was worth a shot but I would still need poudriere for the packages

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
3) Lacks features like live migration (??) and video acceleration(14 ??)

Am I missing something ?
+ Let me know - have an issue opened
