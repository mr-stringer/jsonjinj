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

A simple template is used to write the data structure as JSON to /tmp on the
ansible controler. The file name is based on the hostname and therefore the
output file is overwritten on each run the playbook (unless the file content
doesn't change, but as it contains the date down to the milisecond, this is
unlikely)
