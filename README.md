# jsonjinj

An test ansible playbook that collects data about *nix ansible hosts, places
them in data structure and then writes the data structure as json to the
localhost.

The following information is collected:

* uptime (seconds)
* date (iso8601_micro)
* os (name and version)
* user_count (number of users defined in /etc/passwd)
* kernel_version
* package_count (number of installed packages)
* mounts
  * fstype
  * size (file system size in bytes)
  * used (file system used size in bytes)
  * avail (file system available availble size in bytes)
  * mount (file system mount point)
* disks
  * device
  * sectors, number of
  * sectorsize (bytes)
  * totalsize (bytes)
  * vendor (disk vendor string)
  * wwn