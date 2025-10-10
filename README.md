# [PREAMBLE]

	Thanks for taking interest in paged! This project was originally forked
	from the thttpd project by ACME as it appeared to no longer be in active
	development at the time in 2015. Since then, there have only been two
	releases by the original author, with the last version posted in 2018 -
	close to a decade ago. While there are no official statements indicating
	development has ceased, the absence of releases indicates either no
	further interest, or a very low priority level. Several others have
	attempted to continue this project, but they also all seem to be stale.
	The original project fit very well with our goals as we found it to be a
	lightweight, secure, and very fast web server that exceeded our needs.
	As such we will continue development into the forseeable future. Below
	is a list of work that we intend to accomplish as soon as possible.

		TODO
		- update all the 'thttpd' verbiage and filenames to 'paged'
		- add patches from github.com/blueness/sthttpd/commits/master/
		- add patches from the 2018 code base from ACME (2.28 & 2.29)
		- add a more comprehensive --help output
		- complete 'high priority' list items in TODO file
		- add scripts and documentation to interface with stunnel
		- add patches from other authors (some might be stale now)
		  https://www.evanjones.ca/software/thttpd.html
		  https://www.cs.rice.edu/CS/Architecture/tools/thttpd/
		  https://gitlab.umiacs.umd.edu/netmeasure/scriptroute/-/blob/scriptroute_v0_3_0/patches/thttpd
		  https://git.slackbuilds.org/slackbuilds/plain/network/thttpd/patches/?id=ce7ce5bafeb3ad7ad0f86248df8a6df2f6a7d205
		  https://mirrors.xmission.com/salix/sbo/14.0/network/thttpd/patches/
		  http://thttpd.ludost.net/
		- incorporate TLS/SSL abilities using STunnel
		  https://www.stunnel.org/
		  https://en.wikipedia.org/wiki/Stunnel
		  https://stackoverflow.com/questions/21692357/ssl-connection-for-website-hosting-under-thttpd
		  https://yotsev.xyz/sysadmin/thttpd.html




# [FOR THE IMPATIENT]

	To Compile:
		1. cd /path/to/paged
		2. ./configure
		3. make

	To Install:
		1. cd /path/to/paged
		2. sudo make install

	Examples of Starting:
		# Serving files in pwd on port 80 as user 'www'
		paged -u www -h 192.68.0.15 -l /var/log/paged.log

		# Serving files in pwd on port 12345 as user 'nobody'
		paged -p 12345 -h 192.68.0.15 -l /var/log/paged.log

		# Serving files in '/var/www/html' with shell scripts as cgi
		paged -h 192.68.0.15 -d /var/www/html -c **.sh -l /var/log/paged.log

		# Using a pid file to use signals
		paged -h 192.68.0.15 -i /var/run/paged.pid -l /var/log/paged.log




# [USEFUL FEATURES]

	Being a single file executable usually does not include a rich feature
	set, but similar to our other project pax, this one does not disappoint!
	Weighing in at just over 100kb, this binary packs quite a punch! Here is
	a small list of features that are included:

		- Virtual hosting
		- Very fast file serving
		- Throttling of bandwidth
		- Can chroot for security
		- Interaction via signals
		- Display custom errors
		- Very basic authentication

	Usually when features are packed in, the executable grows very large,
	but this project has managed to maintain a small footprint. The biggest
	issue that is absent is the inclusion of TLS/SSL, which is basically a
	mandatory feature in the world today. While there are no plans to add
	this feature directly into the webserver, there is hope! The stunnel
	project can wrap traffic in that encrypted layer providing this very
	necessary functionality to the project. Both can remain specifically
	focused on their main task, making both projects better.




# [ACKNOWLEDGEMENTS]

	Tremendous credit needs to be extended towards the original author of
	the forked thttpd project, Jef Poskanzer <jef@mail.acme.com>. Without
	his hard work this project certainly would not exist. Credit needs to
	also be extended to the various parties that have contributed patches
	to his original work along the way. And while it is not our intention
	of superceeding the original author, we would like to take the reigns
	so-to-speak and make progress with updating this software as outlined
	above.




# [FUTURE DEV TIMELINE]

	Since we are working with several many projects (13 on github alone),
	we are going to provide an anticipated timeline of releases using
	internal staff. Obviously outside contribution will advance these
	forecasted dates.

	2025 Oct - completion of ModuleMaker for webWorks
	2025 Dec - migration of existing webWorks modules using ModuleMaker
	2026 Jan - migration of Tracker into webWorks and deprecation of
	           of standalone project
	2026 Feb - update paged to 2018 code base from ACME
	         - update pax to work with (TC) TinyCore Linux
	         - apply any patches for bug fixes to existing projects
	2026 Mar - update web.libs for dittodata and web.de
	2026 Jul - move code from web.de into cli.de and update the former
	           to use the latter via XML communication
	2026     - rest of 2026 tbd

