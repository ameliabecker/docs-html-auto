.. _labvm:


Lab VM
~~~~~~

****************************
Read The Docs VMs in the lab
****************************


VPN or at HQ:
ssh amelia.becker@ip.ip.ip.ip


10.11.12.13    rtd.ad.secunetics.com    VM    " - Read the Docs VM (Template)
- POC: Jared Polli
- secadmin/biW$^%tG8aser"



**Start with this one

10.11.12.14    readthedocs.ad.secunetics.com    VM    " - Read the Docs VM
- POC: Jared Polli
- secadmin/biW$^%tG8aser"


10.11.12.15    narm-gitlab.ad.secunetics.com    VM



To do:
- look for rtd
  - Python 3.6 
  - virtualenv
  - Git (version >=2.17.0)
  - Pip (version >1.5)
  - Redis
  - Elasticsearch?


VM 10.11.12.14 Notes:
--old gov't standard baseline

used "sudo su -" to get root access


*exit



Can't log in to 10.11.12.13

10.11.12.15 (narm-gitlab) no git?

********
The plan
********

* ! Snapshot
* install everything on 10.11.12.14
	* Python 3.6
	* git v2.17
	* pip v 1.5
	* virtualenv
	* redis
	* read the docs
* ! snap
* get gitlab
* connect to personal gitlab
  


*****************
Notes 10.11.12.14
*****************

close vm before taking snapshot


Utitities:
==========
* subscription-manager
* sudo su -
* yum install vim -y
* yum install wget -y
* # yum install tcl -y

Install Python3 on RHEL
=======================

* become root
* # subscription-manager (register, attach --auto) working
	* subscription-manager repos \
 	--enable rhel-7-server-optional-rpms \
 	--enable rhel-server-rhscl-7-rpms
* # yum install @development
* # yum install rh-python36
* exit root

* $ scl enable rh-python36 bash
* $ python3 -V
Python 3.6.3
* $ python -V # python now points to Python 3
Python 3.6.3
* $ which python
/opt/rh/rh-python36/root/usr/bin/python


Also installed:
* pip 9.0.1
* virtualenv 15.1.0 (use "python3.6 -m virtualenv")



Installing Git 2.17
===================

	Since git is already installed...

	%for updating git to 2.18 https://tecadmin.net/install-git-on-centos-fedora/
	# yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel
	# yum install gcc perl-ExtUtils-MakeMaker

	# cd /usr/src
	# git clone https://github.com/git/git
	# cd git

	# make prefix=/usr/local/git all
	# make prefix=/usr/local/git install
	# echo "export PATH=/usr/local/git/bin:$PATH" >> /etc/bashrc
	# source /etc/bashrc

Redis
=====

# cd /usr/src
# git clone https://github.com/antirez/redis.git
# cd redis

# make V=1
# make test -s

 *******************************
 When things get F-ed:  rm -r -f
 *******************************



Getting Read The Docs.org
=========================

$ sudo yum install python-devel libxml2-devel libxslt-devel

$ sudo git clone https://github.com/rtfd/readthedocs.org.git
cd readthedocs.org


When reopening a Bash session
=============================



* $ scl enable rh-python36 bash
  


*****************************
RTD VM "Template" 10.11.12.13
*****************************

installed vim

downloaded readthedocs.org




********************************
`LAB VM RUNNING RTD <vm2.html>`_
********************************

post clone--see `VM Part 2 <vm2.html>`_
