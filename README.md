# Nextcloud:apache-full

## What is this?
This is a daily build of the Nextcloud Apache-based image with all of the options (-full) enabled.

## What does this provide?
* cron (via supervisord)
* dependencies for IMAP authentication
* dependencies for accessing SMB / CIFS shares

## How do I use this?
Use this image the same way you would the official Nextcloud image; just replace 'nextcloud:latest' with 'wesleydean/nextcloudapachefull:latest'.

Setup the volume -- do this once, the first time:
```docker volume create nextclouddata```

Pull the image:
```docker pull wesleydean/nextcloudapachefull:latest```

Use this to start the container:
```docker run --detach --volume nextclouddata:/var/www/html --publish 8080:80 --name nextcloud  wesleydean/nextcloudapachefull:latest```

## Where did the source come from?
The Dockerfile used to build this image was provided by the Nextcloud project through their repository on GitHub:

* https://github.com/nextcloud/docker/tree/master/.examples

## How do I get automated updates?
Add a container running 'v2tech/watchtower'; this will check for updated images, pull the updates, and safely restart the affected containers automatically.

* https://hub.docker.com/r/v2tec/watchtower

## Who gets credit for this?
The kind folks who maintain Nextcloud, Docker Hub, GitHub, V2tech, and Jenkins.  All I did was setup a scheduled build to take everyone else's work and push the refreshed image.
