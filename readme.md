# OWASP Honeypot

![Build Status](https://github.com/zdresearch/OWASP-Honeypot/workflows/Python%20application/badge.svg?branch=master) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/5d4f23ebcfb0417e906ed29441f60050)](https://www.codacy.com/app/zdresearch/OWASP-Honeypot?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=zdresearch/OWASP-Honeypot&amp;utm_campaign=Badge_Grade)

OWASP Honeypot is an open-source software in Python language which designed for creating honeypot and honeynet in an easy and secure way! This project is compatible with Python 3.x and tested on Mac OS X, and [Linux](https://github.com/zdresearch/OWASP-Honeypot/actions).

We appreciate any contribution, ideas, feedback. feel free to contact us by creating an issue or send me email directly [ali.razmjoo@owasp.org](mailto:ali.razmjoo@owasp.org). Please visit [Wiki](https://github.com/zdresearch/OWASP-Honeypot/wiki) page for more information.

### Live API
We've setup a live API on a few servers in Stockholm area, you can use API calls and information without any limitation, the service is running on a tiny VPS, please do not send a lot of requests.

* http://ohp-stockholm-live.z3r0d4y.com:5000/

______

##### ***WE ARE IN RESEARCH AND DEVELOP PHASE, EXPECT ERRORS!***

##### ***NO WARRANTY! USE WITH YOUR OWN RESPONSIBILITY!***

##### ***DO NOT USE IT ON THE SAME SERVER(S)/NETWORK WHICH YOU HAVING YOUR PRODUCT/INFORMATION/SENSIBLE DATA***

* Running Example (I sent `ctrl + c` to close and remove honeypot service correctly!)

```

      ______          __      _____ _____
     / __ \ \        / /\    / ____|  __ \
    | |  | \ \  /\  / /  \  | (___ | |__) |
    | |  | |\ \/  \/ / /\ \  \___ \|  ___/
    | |__| | \  /\  / ____ \ ____) | |
     \____/   \/  \/_/    \_\_____/|_|
                      _    _                        _____      _
                     | |  | |                      |  __ \    | |
                     | |__| | ___  _ __   ___ _   _| |__) |__ | |_
                     |  __  |/ _ \| "_ \ / _ \ | | |  ___/ _ \| __|
                     | |  | | (_) | | | |  __/ |_| | |  | (_) | |_
                     |_|  |_|\___/|_| |_|\___|\__, |_|   \___/ \__|
                                               __/ |
                                              |___/

[+] [2018-07-09 23:56:06] OWASP Honeypot started ...
[+] [2018-07-09 23:56:06] loading modules ftp/weak_password, http/basic_auth_weak_password, ssh/weak_password
[+] [2018-07-09 23:56:06] creating image ohp_ftpserver
[+] [2018-07-09 23:56:35] image ohp_ftpserver created
[+] [2018-07-09 23:56:35] creating image ohp_httpserver
[+] [2018-07-09 23:57:00] image ohp_httpserver created
[+] [2018-07-09 23:57:00] creating image ohp_sshserver
[+] [2018-07-09 23:57:17] image ohp_sshserver created
[+] [2018-07-09 23:57:17] creating ohp_internet network
[+] [2018-07-09 23:57:17] ohp_internet network created subnet:172.19.0.0/16 gateway:172.19.0.1
[+] [2018-07-09 23:57:17] creating ohp_no_internet network
[+] [2018-07-09 23:57:18] ohp_no_internet network created subnet:172.20.0.0/16 gateway:172.20.0.1
[+] [2018-07-09 23:57:18] container ohp_ftpserver_weak_password started, forwarding 0.0.0.0:21 to 72.20.0.:21
[+] [2018-07-09 23:57:18] container ohp_httpserver_basic_auth_weak_password started, forwarding 0.0.0.0:80 to 72.20.0.:80
[+] [2018-07-09 23:57:19] container ohp_sshserver_weak_password started, forwarding 0.0.0.0:22 to 72.19.0.:22
[+] [2018-07-09 23:57:19] all selected modules started: ftp/weak_password, http/basic_auth_weak_password, ssh/weak_password
[+] [2018-07-09 23:57:29] interrupted by user, please wait to stop the containers and remove the containers and images
[+] [2018-07-09 23:57:39] stopping container ohp_httpserver_basic_auth_weak_password
[+] [2018-07-09 23:57:49] stopping container ohp_sshserver_weak_password
[+] [2018-07-09 23:57:49] removing container ohp_ftpserver_weak_password
[+] [2018-07-09 23:57:49] removing container ohp_httpserver_basic_auth_weak_password
[+] [2018-07-09 23:57:49] removing container ohp_sshserver_weak_password
[+] [2018-07-09 23:57:49] removing image ohp_sshserver
[+] [2018-07-09 23:57:49] removing image ohp_httpserver
[+] [2018-07-09 23:57:49] removing image ohp_ftpserver
[+] [2018-07-09 23:57:49] finished.

```

### API Actions & WebUI

* Please visit [API Actions](https://github.com/zdresearch/OWASP-Honeypot/wiki/API) in wiki page to find more information
* Use `python ohp.py --start-api-server` to start API Server with [default configuration](https://github.com/zdresearch/OWASP-Honeypot/blob/master/config.py).

#### Run Dockerized API

* To run the API with _MongoDB_ running on the host, use the command given below:

```sh
docker-compose -f docker-compose-host.yml up
```

* To run the API with _MongoDB_ also running on a docker container, use the following commands:

```sh
docker-compose up
```

![image_2018-07-17_01-48-26](https://user-images.githubusercontent.com/7676267/42784742-63f95a2e-8965-11e8-8d64-435f6182dcf2.png)

![ohp](https://user-images.githubusercontent.com/16983076/90905220-29ab0d00-e3d0-11ea-98e4-6b0d3d9c740a.png)


## Contributing

Pull requests are welcome! Feel free to [join us on Slack](https://owasp.slack.com) and discuss the project with the engineers on #owasp-python-honeypot. You are welcome to take any open issue in the tracker labeled 'help wanted' or 'good first issue'. See the [CONTRIBUTORS](https://github.com/zdresearch/OWASP-Honeypot/blob/master/CONTRIBUTING.md) file for details. Other issues are open for contribution as well, but may be less accessible or well defined in comparison to those that are explicitly labeled; you should consider reaching out to us if you are interested in implementing these tickets.
