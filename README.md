# Airfield
Simple [hipache](https://github.com/dotcloud/hipache) web-interface

## Usage with Docker

- Start hipache container, this comes with redis built into the same container

```docker run --name hipache -d hipache```

- Start airfield, linked to the just started hipache container, linked as 'redis', and set username and password

```docker run --link hipache:redis -e AIRFIELD_USER=username -e AIRFIELD_PASS=password -p 3000:3000 -d dhrp/airfield```

- now go to your host ip, port 3000 and you can login with the username and password you've set in the environment
variables


## Normal / manual installation

*After downloading source:*

	cd airfield
	npm install
	node airfield.js

Then you can go to [http://server.com:3000/](http://server.com:3000/)

## Login

Login credentials are set with AIRFIELD_USER and AIRFIELD_PASS environment variables.


## Openstack support

If you are doing lot's of proxying to Openstack instances, you can enable openstack-support.
The management console uses openstack-api to fetch ips, names and statuses of all instances.
This feature is tested with Folsom.
All you have to do is enable it from **settings.js** and change the login credientials in the same file.

**If you are using this for a real purpose not just testing, tweak other settings too.**

## ToDo

 * Better AJAX-message construction
 * Statistics
 * Search
 * Paging
