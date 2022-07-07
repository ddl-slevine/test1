## Install using Docker

### Use a Dockerfile to install the Low Code Assistant™ on top of a base image. Place these instructions in a file named `Dockerfile` in your working directory. 

!!! info "Download Wheel and Install"

    https://private-url/dominocode.tar.gz is a placeholder. Once you have the private download link from your sales team, you can replace the placeholder.

```
# pull from a [Domino base image](https://docs.dominodatalab.com/en/latest/user_guide/0d73c6/domino-standard-environments/#_domino_standard_environment_dse), such as a [Domino DME (Domino Minimal Distribution)](https://quay.io/repository/domino/minimal-environment?tab=tags&tag=latest)
FROM quay.io/domino/minimal-environment:latest

# Optional: Maintainer / Label instructions
LABEL "Customizations"="LCA"

# download wheel and install
RUN wget https://private-url/dominocode.tar.gz
RUN pip install dominocode.tar.gz.whl
```

### Build the Image 

```
docker build --progress=plain -f Dockerfile . 
