
# Use the latest version of the docker image.
If you are using CircleCI, point the image to the latest version like this:
```bash
docker:
  - image: frontlinemdedge/frontlinedocker:latest
```

# Updating Docker Image Using a Tag

In order to update the docker image, checkout this repo and update the docker 
file and then push to the master branch. That should trigger a new build on the
docker image.

In circle ci, as long as you are pointing to the latest tag with 
"chrisroane/frontlinedocker:latest", it should automatically pull down the
latest docker image.
