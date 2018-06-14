
# Use the latest version of the docker image.
If you are using CircleCI, point the image to the latest version like this:
```bash
docker:
  - image: chrisroane/frontlinedocker:latest
```

# Updating Docker Image Using a Tag

In order to publish a new docker file, follow these instructions. Make sure to update
the version number to the new tag name in all commands.

First cd into this directory where the Dockerfile is located.

To generate a new docker build based on what is in the Dockerfile, run this command:
```bash
docker build -t "chrisroane/frontlinedocker:0.0.13" .
```

Once your docker file builds successfully, you will want to log into the docker container. This docker run command gives a local "name". If you need to run this multiple times from the same tag, increment the last number each time to give it a unique name.
```bash
docker run --name frontline-portal-013-1 -it "chrisroane/frontlinedocker:0.0.13" /bin/bash
```

Once you are logged into the docker container, grab the "hash" value. This value is right after the `root@` text.
```bash
docker commit 9e2445d797be chrisroane/ffrontlinedocker:0.0.13
```

Finally, push up the latest image.
```bash
docker push chrisroane/frontlinedocker:0.0.13
```

If you are using CircleCI, make sure you update the .circleci/.config.yml to point to the new tag version.
