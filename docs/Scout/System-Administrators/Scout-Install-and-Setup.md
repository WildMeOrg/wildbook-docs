# Scout Installation and Startup

System setup must be completed before you can complete Scout Installation.

## Installation

$$INFO
title: Important
You must be connected to the Internet for the initial installation.
$$

Enter the following in the Ubuntu Terminal: `docker pull wildme/scout:latest` to pull the latest container version of Scout.

## Setup

$$INFO
title: Info
Now that you've successfully installed Scout, you can work offline or online to complete setup.
$$

Enter the run command in the Ubuntu Terminal to launch Scout for setup. 

**GPU processing with System File Storage**
`` docker run --privileged -p 1337:1337 --rm -it --gpus all --mount type=bind,source=/data,target=/data -e ENV_IP="`ip route get 1 | sed 's/^.*src \([^ ]*\).*$/\1/;q'`" -v /data/scout/db:/data/db -v /data/scout/tmp:/tmp/scout-tmp wildme/scout:latest``


During first installation, you are prompted to enter a source image directory where the images are stored.
 
Enter the full path of the upload image directory based on your configuration:

* Image storage: /data/scout/images
* System File Storage: /data/scout/db:/data/db and /data/scout/tmp:/tmp/scout-tmp

A successful Scout installation provides some critical information that a *Lab Lead* needs. This includes:

* **Scout URL and port for browser access**: This URL should be provided directly to the Lab Lead when your Scout Server is finally running. Open a Chrome browser and go to [http://10.0.0.104:1337 ](http://10.0.0.104:1337/).

$$INFO
title: Info
If your server has a hostname such as “scoutserver”, you should also be able to use http://scoutserver.local:1337
$$

* **Password override token**: This token is only needed if the Lab Lead forgets their password and cannot sign in. This token changes with every restart of Scout. Your password override token is: `lccmnvxw6j`. Paste this token in place of your password to log in (you can then change your password).

Setup is complete after providing the Lab Lead the Scout Server URL and image directory full path on the NAS.