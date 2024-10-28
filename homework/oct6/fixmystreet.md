Steps I took to fork, clone, and set up FixMyStreet

Step 1: Forking the FixMyStreet Repository

First, I needed to fork the FixMyStreet repository to my own GitHub account.

I went to the FixMyStreet GitHub repository.
I clicked the Fork button at the top right, creating a personal copy of the repository in my account.

Step 2: Cloning the Forked Repository
After forking the repository, I cloned it to my local machine to start working with it.

In the terminal, I ran the following command to clone the repo:
```bash
git clone https://github.com/abrararpon/fixmystreet.git
```
```bash
Cloning into 'fixmystreet'...
remote: Enumerating objects: 152444, done.
remote: Counting objects: 100% (4568/4568), done.
remote: Compressing objects: 100% (2287/2287), done.
remote: Total 152444 (delta 2980), reused 3270 (delta 2177), pack-reused 147876 (from 1)
Receiving objects: 100% (152444/152444), 176.65 MiB | 68.99 MiB/s, done.
Resolving deltas: 100% (110391/110391), done.
Updating files: 100% (4336/4336), done.
```
Then, I navigated into the cloned directory:
```bash
cd fixmystreet
```
Step 3: Running FixMyStreet with Docker
Next, I ran FixMyStreet using Docker. This was simple because FixMyStreet provides a Docker setup to make everything work out of the box.
Before continuing, I ensured Docker the docker version:

```bash
docker --version
```
```bash

```
After confirming that the docker was installed, I continued.

I used Docker Compose to build and start the FixMyStreet environment:

```bash
docker-compose up
```

<details>
  <summary><u>show output</u></summary>
  
```bash
WARN[0000] /Users/abraararpon/os_abraar/fixmystreet/docker-compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion 
[+] Running 5/5
 ✔ Network fixmystreet_default          Created                                                                     0.3s 
 ✔ Container fixmystreet-memcached-1    Created                                                                     1.1s 
 ✔ Container fixmystreet-postgres-1     Created                                                                     1.8s 
 ✔ Container fixmystreet-fixmystreet-1  Created                                                                     1.1s 
 ✔ Container fixmystreet-nginx-1        Created                                                                     0.4s 
Attaching to fixmystreet-1, memcached-1, nginx-1, postgres-1
postgres-1     | LOG:  database system was shut down at 2024-09-24 23:48:28 UTC
postgres-1     | LOG:  MultiXact member wraparound protections are now enabled
postgres-1     | LOG:  autovacuum launcher started
postgres-1     | LOG:  database system is ready to accept connections
fixmystreet-1  | run-parts: executing /usr/local/preinit/00-checkroot
fixmystreet-1  | Cleaning up; ignore errors here:
[FAILstreet-1  | [....] Cleaning up temporary files... /tmp /run /run/lock failed!
fixmystreet-1  | run-parts: executing /usr/local/preinit/00-setinit
fixmystreet-1  | run-parts: executing /usr/local/preinit/01-syslog
fixmystreet-1  | Sending syslog to Docker (config file /etc/syslog.conf.stdout)
fixmystreet-1  | run-parts: executing /usr/local/preinit/01-timezone
fixmystreet-1  | run-parts: executing /usr/local/preinit/02-ssh-server
fixmystreet-1  | SSH server disabled; set DEBBASE_SSH=enabled to enable
fixmystreet-1  | run-parts: executing /usr/local/preinit/99-fixmystreet
fixmystreet-1  | Testing connection to postgres.svc.
fixmystreet-1  | Done.
fixmystreet-1  | ERROR:  role "fms" already exists
postgres-1     | ERROR:  role "fms" already exists
postgres-1     | STATEMENT:  create user "fms" with CREATEDB password 'fms'
Ign:1 http://security.debian.org/debian-security stretch/updates InRelease
Ign:2 http://deb.debian.org/debian stretch InRelease
Ign:3 http://deb.debian.org/debian stretch-updates InRelease
Ign:4 http://security.debian.org/debian-security stretch/updates Release
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:6 http://deb.debian.org/debian stretch Release
Ign:7 http://deb.debian.org/debian stretch-updates Release
Ign:8 http://deb.debian.org/debian stretch/main all Packages
Ign:9 http://deb.debian.org/debian stretch/main amd64 Packages             
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages      
Ign:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages    
Ign:8 http://deb.debian.org/debian stretch/main all Packages                   
Ign:9 http://deb.debian.org/debian stretch/main amd64 Packages                 
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages          
Ign:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages        
Ign:8 http://deb.debian.org/debian stretch/main all Packages                   
Ign:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
Ign:9 http://deb.debian.org/debian stretch/main amd64 Packages      
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages
Ign:13 http://the.earth.li/debian stretch InRelease                 
Ign:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages
Ign:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
Ign:8 http://deb.debian.org/debian stretch/main all Packages
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:14 http://the.earth.li/debian stretch Release                   
Ign:9 http://deb.debian.org/debian stretch/main amd64 Packages
Ign:15 http://the.earth.li/debian stretch/main Sources              
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages
Ign:16 http://the.earth.li/debian stretch/non-free Sources          
Ign:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages
Ign:8 http://deb.debian.org/debian stretch/main all Packages        
Ign:18 http://the.earth.li/debian stretch/main all Packages         
Ign:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:9 http://deb.debian.org/debian stretch/main amd64 Packages      
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages   
Ign:21 http://the.earth.li/debian stretch/non-free all Packages     
Ign:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
Ign:5 http://security.debian.org/debian-security stretch/updates/main all Packages
Ign:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages
Ign:8 http://deb.debian.org/debian stretch/main all Packages        
Ign:22 http://the.earth.li/debian stretch/contrib all Packages      
Err:12 http://security.debian.org/debian-security stretch/updates/main amd64 Packages
fixmystreet-1  |   404  Not Found
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Err:9 http://deb.debian.org/debian stretch/main amd64 Packages
fixmystreet-1  |   404  Not Found
Ign:10 http://deb.debian.org/debian stretch-updates/main all Packages
Ign:15 http://the.earth.li/debian stretch/main Sources
Err:11 http://deb.debian.org/debian stretch-updates/main amd64 Packages
fixmystreet-1  |   404  Not Found
Ign:16 http://the.earth.li/debian stretch/non-free Sources
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:18 http://the.earth.li/debian stretch/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages
Ign:21 http://the.earth.li/debian stretch/non-free all Packages
Ign:22 http://the.earth.li/debian stretch/contrib all Packages
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Ign:15 http://the.earth.li/debian stretch/main Sources
Ign:16 http://the.earth.li/debian stretch/non-free Sources
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:18 http://the.earth.li/debian stretch/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages
Ign:21 http://the.earth.li/debian stretch/non-free all Packages
Ign:22 http://the.earth.li/debian stretch/contrib all Packages
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Ign:15 http://the.earth.li/debian stretch/main Sources
Ign:16 http://the.earth.li/debian stretch/non-free Sources
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:18 http://the.earth.li/debian stretch/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages
Ign:21 http://the.earth.li/debian stretch/non-free all Packages
Ign:22 http://the.earth.li/debian stretch/contrib all Packages
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Ign:15 http://the.earth.li/debian stretch/main Sources
Ign:16 http://the.earth.li/debian stretch/non-free Sources
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:18 http://the.earth.li/debian stretch/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages
Ign:21 http://the.earth.li/debian stretch/non-free all Packages
Ign:22 http://the.earth.li/debian stretch/contrib all Packages
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Err:15 http://the.earth.li/debian stretch/main Sources
fixmystreet-1  |   404  Not Found
Ign:16 http://the.earth.li/debian stretch/non-free Sources
Ign:17 http://the.earth.li/debian stretch/contrib Sources
Ign:18 http://the.earth.li/debian stretch/main all Packages
Ign:19 http://the.earth.li/debian stretch/contrib amd64 Packages
Ign:20 http://the.earth.li/debian stretch/non-free amd64 Packages
Ign:21 http://the.earth.li/debian stretch/non-free all Packages
Ign:22 http://the.earth.li/debian stretch/contrib all Packages
Ign:23 http://the.earth.li/debian stretch/main amd64 Packages
Reading package lists... Done
fixmystreet-1  | W: The repository 'http://security.debian.org/debian-security stretch/updates Release' does not have a Release file.
fixmystreet-1  | N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
fixmystreet-1  | N: See apt-secure(8) manpage for repository creation and user configuration details.
fixmystreet-1  | W: The repository 'http://deb.debian.org/debian stretch Release' does not have a Release file.
fixmystreet-1  | N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
fixmystreet-1  | N: See apt-secure(8) manpage for repository creation and user configuration details.
fixmystreet-1  | W: The repository 'http://deb.debian.org/debian stretch-updates Release' does not have a Release file.
fixmystreet-1  | N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
fixmystreet-1  | N: See apt-secure(8) manpage for repository creation and user configuration details.
fixmystreet-1  | W: The repository 'http://the.earth.li/debian stretch Release' does not have a Release file.
fixmystreet-1  | N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
fixmystreet-1  | N: See apt-secure(8) manpage for repository creation and user configuration details.
fixmystreet-1  | E: Failed to fetch http://security.debian.org/debian-security/dists/stretch/updates/main/binary-amd64/Packages  404  Not Found
fixmystreet-1  | E: Failed to fetch http://deb.debian.org/debian/dists/stretch/main/binary-amd64/Packages  404  Not Found
fixmystreet-1  | E: Failed to fetch http://deb.debian.org/debian/dists/stretch-updates/main/binary-amd64/Packages  404  Not Found
fixmystreet-1  | E: Failed to fetch http://the.earth.li/debian/dists/stretch/main/source/Sources  404  Not Found
fixmystreet-1  | E: Some index files failed to download. They have been ignored, or old ones used instead.
fixmystreet-1  | Installing modules using /var/www/fixmystreet/fixmystreet/cpanfile (deployment mode)
fixmystreet-1  | Complete! Modules were installed into /var/www/fixmystreet/fixmystreet/local
nginx-1        | 2024/10/06 07:42:07 [error] 7#7: *1 connect() failed (111: Connection refused) while connecting to upstream, client: 192.168.65.1, server: , request: "GET / HTTP/1.1", upstream: "http://172.19.0.4:9000/", host: "localhost:8000"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:42:07 +0000] "GET / HTTP/1.1" 502 575 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 2024/10/06 07:42:09 [error] 7#7: *1 connect() failed (111: Connection refused) while connecting to upstream, client: 192.168.65.1, server: , request: "GET /favicon.ico HTTP/1.1", upstream: "http://172.19.0.4:9000/favicon.ico", host: "localhost:8000", referrer: "http://localhost:8000/"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:42:09 +0000] "GET /favicon.ico HTTP/1.1" 502 575 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 2024/10/06 07:42:12 [error] 7#7: *1 connect() failed (111: Connection refused) while connecting to upstream, client: 192.168.65.1, server: , request: "GET /service-worker.js HTTP/1.1", upstream: "http://172.19.0.4:9000/service-worker.js", host: "localhost:8000", referrer: "http://localhost:8000/service-worker.js"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:42:12 +0000] "GET /service-worker.js HTTP/1.1" 502 575 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
fixmystreet-1  | Current database version = 0074
fixmystreet-1  | Nothing to do
fixmystreet-1  | locale/ar.UTF-8 FixMyStreet.po: 835 translated messages, 58 fuzzy translations, 333 untranslated messages.
fixmystreet-1  | locale/bg_BG.UTF-8 FixMyStreet.po: 430 translated messages, 38 fuzzy translations, 758 untranslated messages.
fixmystreet-1  | locale/ca_ES.UTF-8 FixMyStreet.po: 239 translated messages, 21 fuzzy translations, 966 untranslated messages.
fixmystreet-1  | locale/cs_CZ.UTF-8 FixMyStreet.po: 520 translated messages, 40 fuzzy translations, 666 untranslated messages.
fixmystreet-1  | locale/cy_GB.UTF-8 EmptyHomes.po: 674 translated messages, 43 fuzzy translations, 59 untranslated messages.
fixmystreet-1  | locale/cy.UTF-8 FixMyStreet.po: 336 translated messages, 34 fuzzy translations, 856 untranslated messages.
fixmystreet-1  | locale/da_DK.UTF-8 FixMyStreet.po: 553 translated messages, 41 fuzzy translations, 632 untranslated messages.
fixmystreet-1  | locale/de_CH.UTF-8 FixMyStreet.po: 369 translated messages, 40 fuzzy translations, 817 untranslated messages.
fixmystreet-1  | locale/de_DE.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 898 translated messages, 15 fuzzy translations, 313 untranslated messages.
fixmystreet-1  | locale/el_GR.UTF-8 FixMyStreet.po: 639 translated messages, 50 fuzzy translations, 537 untranslated messages.
fixmystreet-1  | locale/es_DO.UTF-8 FixMyStreet.po: 757 translated messages, 54 fuzzy translations, 415 untranslated messages.
fixmystreet-1  | locale/es_ES.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 967 translated messages, 13 fuzzy translations, 246 untranslated messages.
fixmystreet-1  | locale/es.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 967 translated messages, 13 fuzzy translations, 246 untranslated messages.
fixmystreet-1  | locale/fa_IR.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 685 translated messages, 14 fuzzy translations, 527 untranslated messages.
fixmystreet-1  | locale/fr_FR.UTF-8 FixMyStreet.po: 1065 translated messages, 65 fuzzy translations, 96 untranslated messages.
fixmystreet-1  | locale/he_IL.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 329 translated messages, 9 fuzzy translations, 888 untranslated messages.
fixmystreet-1  | locale/hr.UTF-8 FixMyStreet.po: 746 translated messages, 54 fuzzy translations, 426 untranslated messages.
fixmystreet-1  | locale/hu_HU.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 49 translated messages, 3 fuzzy translations, 1174 untranslated messages.
fixmystreet-1  | locale/id_ID.UTF-8 FixMyStreet.po: 816 translated messages, 54 fuzzy translations, 356 untranslated messages.
fixmystreet-1  | locale/it.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 564 translated messages, 11 fuzzy translations, 651 untranslated messages.
fixmystreet-1  | locale/lt_LT.UTF-8 FixMyStreet.po: 309 translated messages, 29 fuzzy translations, 888 untranslated messages.
fixmystreet-1  | locale/ms.UTF-8 FixMyStreet.po: 383 translated messages, 34 fuzzy translations, 809 untranslated messages.
fixmystreet-1  | locale/my_MM.UTF-8 FixMyStreet.po: 342 translated messages, 34 fuzzy translations, 850 untranslated messages.
fixmystreet-1  | locale/nb_NO.UTF-8 FixMyStreet.po: 789 translated messages, 57 fuzzy translations, 380 untranslated messages.
fixmystreet-1  | locale/nl_NL.UTF-8 FixMyStreet.po: 423 translated messages, 34 fuzzy translations, 769 untranslated messages.
fixmystreet-1  | locale/nn_NO.UTF-8 FixMyStreet.po: 349 translated messages, 30 fuzzy translations, 847 untranslated messages.
fixmystreet-1  | locale/pl_PL.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 143 translated messages, 5 fuzzy translations, 1078 untranslated messages.
fixmystreet-1  | locale/pt_BR.UTF-8 FixMyStreet.po: 1195 translated messages, 17 fuzzy translations, 14 untranslated messages.
fixmystreet-1  | locale/pt_CV.UTF-8 FixMyStreet.po: 1081 translated messages, 66 fuzzy translations, 79 untranslated messages.
fixmystreet-1  | locale/pt.UTF-8 FixMyStreet.po: 1081 translated messages, 66 fuzzy translations, 79 untranslated messages.
fixmystreet-1  | locale/ro_RO.UTF-8 FixMyStreet.po: 22 translated messages, 4 fuzzy translations, 1200 untranslated messages.
fixmystreet-1  | locale/ru.UTF-8 FixMyStreet.po: 615 translated messages, 43 fuzzy translations, 568 untranslated messages.
fixmystreet-1  | locale/sl_SI.UTF-8 FixMyStreet.po: 326 translated messages, 39 fuzzy translations, 861 untranslated messages.
fixmystreet-1  | locale/sq.UTF-8 FixMyStreet.po: 726 translated messages, 52 fuzzy translations, 448 untranslated messages.
fixmystreet-1  | locale/sr.UTF-8 FixMyStreet.po: 621 translated messages, 49 fuzzy translations, 556 untranslated messages.
fixmystreet-1  | locale/sv_SE.UTF-8 FixMyStreet.po: msgfmt: FixMyStreet.po: warning: PO file header fuzzy
fixmystreet-1  |                         warning: older versions of msgfmt will give an error on this
fixmystreet-1  | 1194 translated messages, 17 fuzzy translations, 15 untranslated messages.
fixmystreet-1  | locale/tr_TR.UTF-8 FixMyStreet.po: 603 translated messages, 45 fuzzy translations, 578 untranslated messages.
fixmystreet-1  | locale/uk_UA.UTF-8 FixMyStreet.po: 551 translated messages, 43 fuzzy translations, 632 untranslated messages.
fixmystreet-1  | locale/zh.UTF-8 FixMyStreet.po: 603 translated messages, 43 fuzzy translations, 580 untranslated messages.
fixmystreet-1  | superuser@example.org is now a superuser.
fixmystreet-1  | Starting sysvinit
INIT: version 2.88 booting
fixmystreet-1  | [info] Using makefile-style concurrent boot in runlevel S.
[ ok street-1  | [....] Setting up X socket directories... /tmp/.X11-unix /tmp/.ICE-unix.
INIT: Entering runlevel: 2
fixmystreet-1  | [info] Using makefile-style concurrent boot in runlevel 2.
fixmystreet-1  | Oct  6 07:42:46 97213fbd8f55 syslogd (GNU inetutils 1.9.4): restart
[ ok street-1  | [....] Starting system log daemon: syslogd.
fixmystreet-1  | Oct  6 07:42:46 97213fbd8f55 cron[728]: (CRON) INFO (pidfile fd = 3)
fixmystreet-1  | Oct  6 07:42:46 97213fbd8f55 anacron[733]: Anacron 2.3 started on 2024-10-06
[ ok street-1  | [....] Starting anac(h)ronistic cron: anacron.
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 cron[752]: (CRON) STARTUP (fork ok)
[ ok street-1  | [....] Starting periodic command scheduler: cron.
[ ok street-1  | [....] Starting deferred execution scheduler: atd.
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 anacron[733]: Will run job `cron.daily' in 5 min.
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 anacron[733]: Will run job `cron.weekly' in 10 min.
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 anacron[733]: Will run job `cron.monthly' in 15 min.
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 anacron[733]: Jobs will be executed sequentially
[warnstreet-1  | [....] No PostgreSQL clusters exist; see "man pg_createcluster" ... (warning).
fixmystreet-1  | Oct  6 07:42:47 97213fbd8f55 cron[752]: (CRON) INFO (Running @reboot jobs)
[ ok street-1  | [....] Starting system message bus: dbus.
[ ok street-1  | [....] Starting Postfix Mail Transport Agent: postfix.
fixmystreet-1  | Oct  6 07:42:52 97213fbd8f55 postfix/master[945]: daemon started -- version 3.1.15, configuration /etc/postfix
fixmystreet-1  | 
fixmystreet-1  | DEPRECATION WARNING: The Regex dispatch type is deprecated.
fixmystreet-1  |   It is recommended that you convert Regex and LocalRegex 
fixmystreet-1  |   methods to Chained methods. at /var/www/fixmystreet/fixmystreet/local/lib/perl5/Catalyst/DispatchType/Regex.pm line 210.
fixmystreet-1  | Oct  6 07:43:35 97213fbd8f55 su[654]: pam_unix(su:session): session closed for user fms
INIT: no more processes left in this runlevel
fixmystreet-1  | Oct  6 07:43:35 97213fbd8f55 init: no more processes left in this runlevel
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:08 +0000] "GET / HTTP/1.1" 200 3481 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /js/loading-attribute-polyfill.js?1605608422 HTTP/1.1" 200 3147 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /vendor/jquery.validate.min.js?1605608422 HTTP/1.1" 200 9052 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /cobrands/fixmystreet/images/site-logo.svg HTTP/1.1" 200 3167 "http://localhost:8000/cobrands/default/base.css?1605609761" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /js/translation_strings.en-gb.js?480055 HTTP/1.1" 200 1399 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /cobrands/fixmystreet/images/fms-platform-logo.svg HTTP/1.1" 200 5456 "http://localhost:8000/cobrands/default/layout.css?1605609761" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /vendor/jquery.multi-select.min.js?1605608422 HTTP/1.1" 200 2128 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /cobrands/fixmystreet/fixmystreet.js?1605608422 HTTP/1.1" 200 21557 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /js/map-OpenLayers.js?1605608422 HTTP/1.1" 200 15953 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /vendor/OpenLayers/OpenLayers.wfs.js?1605608422 HTTP/1.1" 200 111782 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /vendor/fancybox/jquery.fancybox-1.3.4.pack.js?1605608422 HTTP/1.1" 200 6126 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:09 +0000] "GET /vendor/dropzone.min.js?1605608422 HTTP/1.1" 200 13214 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:10 +0000] "GET /favicon.ico HTTP/1.1" 200 15086 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:10 +0000] "GET /.well-known/manifest.webmanifest HTTP/1.1" 200 350 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:10 +0000] "GET /cobrands/fixmystreet/images/192.png HTTP/1.1" 200 6327 "http://localhost:8000/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /service-worker.js HTTP/1.1" 200 1500 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /cobrands/default/layout.css?1605609761 HTTP/1.1" 200 3888 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /cobrands/default/base.css?1605609761 HTTP/1.1" 200 19182 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /vendor/OpenLayers/theme/default/style.css?1605608422 HTTP/1.1" 200 3048 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /vendor/fancybox/jquery.fancybox-1.3.4.css?1605608422 HTTP/1.1" 200 2105 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /js/translation_strings.en-gb.js?480055 HTTP/1.1" 200 1399 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:12 +0000] "GET /offline/fallback?1605608421 HTTP/1.1" 200 2558 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
nginx-1        | 192.168.65.1 - - [06/Oct/2024:07:44:42 +0000] "GET /service-worker.js HTTP/1.1" 200 1500 "http://localhost:8000/service-worker.js" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36" "-"
fixmystreet-1  | Oct  6 07:45:01 97213fbd8f55 CRON[977]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 07:45:01 97213fbd8f55 CRON[978]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 07:45:03 97213fbd8f55 CRON[977]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 07:47:01 97213fbd8f55 CRON[986]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 07:47:01 97213fbd8f55 CRON[987]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/open311-populate-service-list.lock" "/var/www/fixmystreet/fixmystreet/bin/open311-populate-service-list" || echo "stalled?")
fixmystreet-1  | Oct  6 07:47:02 97213fbd8f55 CRON[986]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 07:47:46 97213fbd8f55 anacron[733]: Job `cron.daily' started
fixmystreet-1  | Oct  6 07:47:46 97213fbd8f55 anacron[999]: Updated timestamp for job `cron.daily' to 2024-10-06
fixmystreet-1  | Oct  6 07:50:01 97213fbd8f55 CRON[1008]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 07:50:01 97213fbd8f55 CRON[1009]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 07:50:02 97213fbd8f55 CRON[1008]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 07:52:01 97213fbd8f55 CRON[1017]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 07:52:01 97213fbd8f55 CRON[1018]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-questionnaires.lock" "/var/www/fixmystreet/fixmystreet/bin/send-questionnaires" || echo "stalled?")
fixmystreet-1  | Oct  6 07:52:03 97213fbd8f55 CRON[1017]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 07:55:01 97213fbd8f55 CRON[1026]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 07:55:01 97213fbd8f55 CRON[1027]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 07:55:02 97213fbd8f55 CRON[1026]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1035]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1037]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1036]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1039]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1038]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/bin/check-for-zombies" fms)
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1040]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/bin/send-failure-summary")
fixmystreet-1  | Oct  6 08:00:01 97213fbd8f55 CRON[1035]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:00:03 97213fbd8f55 CRON[1037]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:00:04 97213fbd8f55 CRON[1036]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:02:01 97213fbd8f55 CRON[1051]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:02:01 97213fbd8f55 CRON[1052]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-alerts.lock" "/var/www/fixmystreet/fixmystreet/bin/send-alerts" || echo "stalled?")
fixmystreet-1  | Oct  6 08:02:02 97213fbd8f55 CRON[1051]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 anacron[733]: Job `cron.daily' terminated (exit status: 1) (mailing output)
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 anacron[733]: Job `cron.weekly' started
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 anacron[1188]: Updated timestamp for job `cron.weekly' to 2024-10-06
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 postfix/pickup[963]: 49F7332A8E4: uid=0 from=<root>
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 postfix/cleanup[1193]: 49F7332A8E4: message-id=<20241006080307.49F7332A8E4@3ebed3792ace>
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 postfix/qmgr[964]: 49F7332A8E4: from=<root@3ebed3792ace>, size=521, nrcpt=1 (queue active)
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 postfix/local[1195]: 49F7332A8E4: to=<root@3ebed3792ace>, orig_to=<root>, relay=local, delay=0.29, delays=0.17/0.1/0/0.02, dsn=2.0.0, status=sent (delivered to mailbox)
fixmystreet-1  | Oct  6 08:03:07 97213fbd8f55 postfix/qmgr[964]: 49F7332A8E4: removed
fixmystreet-1  | Oct  6 08:03:09 97213fbd8f55 anacron[733]: Job `cron.weekly' terminated
fixmystreet-1  | Oct  6 08:03:09 97213fbd8f55 anacron[733]: Job `cron.monthly' started
fixmystreet-1  | Oct  6 08:03:09 97213fbd8f55 anacron[733]: Job `cron.monthly' terminated
fixmystreet-1  | Oct  6 08:03:09 97213fbd8f55 anacron[733]: Normal exit (3 jobs run)
fixmystreet-1  | Oct  6 08:03:09 97213fbd8f55 anacron[1200]: Updated timestamp for job `cron.monthly' to 2024-10-06
fixmystreet-1  | Oct  6 08:05:01 97213fbd8f55 CRON[1201]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:05:01 97213fbd8f55 CRON[1202]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 08:05:03 97213fbd8f55 CRON[1201]: pam_unix(cron:session): session closed for user fms
fixmystreet-1  | Oct  6 08:10:01 97213fbd8f55 CRON[1210]: pam_unix(cron:session): session opened for user fms by (uid=0)
fixmystreet-1  | Oct  6 08:10:01 97213fbd8f55 CRON[1211]: (fms) CMD ("/var/www/fixmystreet/fixmystreet/commonlib/bin/run-with-lockfile.sh" -n "/var/www/fixmystreet/send-reports.lock" "/var/www/fixmystreet/fixmystreet/bin/send-reports" || echo "stalled?")
fixmystreet-1  | Oct  6 08:10:02 97213fbd8f55 CRON[1210]: pam_unix(cron:session): session closed for user fms


```
</details>


Docker pulled all necessary images and built the application. The setup also configured the database and web server. I watched the terminal output as the containers were built.

Step 4: Accessing FixMyStreet Locally

Once Docker finished setting up, I was able to access FixMyStreet on my browser.

I opened my browser and typed http://localhost:8000 into the address bar.
FixMyStreet loaded successfully, and I was able to see the app running locally!


