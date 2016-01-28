# woodlouse
Woodlouuse - No-IP script for provider Gandi.net
###########################################################################
NextGen Woodlouse TEST v1.1.4 - No-IP script for provider Gandi.net
###########################################################################

Sergio Fernandez Cordero <sergio@fernandezcordero.net>
twitter: http: //twitter.com/elautoestopista
http://www.fernandezcordero.net/blog

1. CHANGELOG
2. LICENSE AND DISCLAIMER
3. USAGE
4. Log rotation (LINUX / UNIX)
5. Paralel executions
6. AUTHOR'S NOTE

1.CHANGELOG
------------

Implemented the new system logs: Now executions are recorded in the logs / file and operations.log
changes in log file entry / changes.log, including rotation. (Issue # 3)


2.- LICENSE AND DISCLAIMER
---------------------------

License GPLv3 - https://www.gnu.org/copyleft/gpl.html - see LICENSE for details

3.- USAGE
--------

Usage: python woodlouse zone ttl registry apikey (prod / test)

To use the script, you will have first gather some information from the web on your domain Gandi:

zone: DNS name assigned to the domain Zone. When the record is created, it will be created for all domains
using that area.

ttl: The lifetime should be a very low value, so that other DNS servers have little time entry
cached, so they have to frequently check and take the changes that occur. For instance
5 minutes or less.

Registry: Registry value you want to create, without the domain name (as an area can be used in multiple domains).
For example: To create "www.midominio.com" record would be "www".

APIkey: API key provided by Gandi.net to enable the use of the API.

(Prod / test): The modifier prod launches operations into the production environment, the changes are real.
The switch test launch operations against the OT & E environment, there exist only operations.
NOTE: Be sure to create a consistent environment in OT & E before you begin tinkering (check the
API documentation Gandi (http://doc.rpc.gandi.net/)

4.- log rotation (Linux / UNIX)
---------------------------------------

An example of log rotation using logrotate in woodlouse.rotation file is included. To set this rotation to continue
the next steps:

- Install logrotate if not installed:

apt-get install logrotate
urpmi logrotate
yum install logrotate

- If you run woodlouse a non-root user (recommended), add this line to the sudoers file as root:

ALL = NOPASSWD user: / usr / sbin / logrotate

- Add the following line in the crontab of the user running woodlouse

* 0 * * * sudo / usr / sbin / logrotate /ruta-de-instalacion/woodlouse/woodlouse.rotation

- Adjust settings according to your preferences file woodlouse.rotation (more information in the file and http://linux.die.net/man/8/logrotate)

5. Paralel executions
---------------------

For execute more than one woodlouse.py process, usage of run-one is recommended, since woodlouse has no locking system attached.

6. AUTHOR'S NOTE
-------------------

This program is a work in progress. It just works, but can be made better.
Unfortunately, I got no time to finish this work and maintain it, also I don't need anymore this functionality that could be important to me.
But perhaps this code is useful to somebody.

This work is dedicated to my baby Noelia, my beloved "woodlouse" :)
