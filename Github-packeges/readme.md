export GH_USERNAME='my-first-org-41'
export GH_TOKEN=''
GH_IMAGE_NAME='hello-world'
export GH_VER='1.0.1'
echo $GH_TOKEN | docker login ghcr.io -u $GH_USERNAME --password-stdin
export TAG_NAME='ghcr.io/my-first-org-41/hello-world:1.0.1'
docker tag hello-world:latest $TAG_NAME
docker push $TAG_NAME

### Add the user name they have in lowercase not uppercase
