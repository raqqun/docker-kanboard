# Install

`git clone --recurse-submodules git@github.com:raqqun/docker-kanboard.git`


# Build

To build images and run containers, execute:

`docker-compose up -d --build`

Then visit [localhost](http://localhost/). Enter admin/admin as default username/password.

*Ensure nothing's running on port 80*


# Cleanup

To cleanup your environment and startover, execute:

`docker-compose down --rmi all`


# Deploy with ansible

Requirements:

 - Install python docker SDK
    - `pip install docker`
 - Ensure you have a local docker client installed and ponting to a docker API.

To deploy locally with ansible, execute:

`ansible-playbook deploy.yml`


*Ensure prior cleanup before executing the playbook or else eaddrinuse :S*
