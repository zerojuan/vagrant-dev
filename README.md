# Julius' Development Environment

## Features
- fish
- awscli
- git
- nvm


## Assumptions
- because node versions vary per project, it's better to nvm install manually
- uses a netrc file for storing git repo credentials
- secrets are kept in `keys.yml` files

- disable `firewalld` for port-forwarding to work
  - `systemctl stop firewalld` - to stop the service
  - `systemctl disable firewalld` - so it won't restart when you do Vagrant up
