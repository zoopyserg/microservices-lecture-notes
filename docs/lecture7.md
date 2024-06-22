# Deploy

## Important aspects of deployment
- Speed
- Convenience
- Scaling
- Reliability
- Security

## Types
- Manual (rarely used)
- Tools (e.g. Capistrano)
- Cloud SaaS (e.g. Heroku)

## Tools
- Puppet
- Chef
- Ansible
- SaaS (Heroku, AWS, MCS, Yandex Cloud)

## Ansible
- Supported by RedHat
- Agentless
- Uses YAML
- Has many modules

## Ansible Structure
- Control node
- Playbooks
- Inventory
- Modules
- Plugins
- Servers

## Deployment schema
- Open nginx port
- Open rabbitmq port
- The rest is closed

## Preparation
- Server (1 CPU / 1 GB RAM / 25 GB SSD)
- passwordless sudo
- ufw

## Ansible playbooks
- install ansible
- mkdir playbooks
- cd playbooks
- I prefer Capistrano
- But Ansible is a Chef replacement, not Capistrano replacement
- A separate YML file for each system that I need to install
  - for RabbitMQ
  - for PostgreSQL
  - for Nginx
  - etc.

## Deployment of ruby microservices
- Push to GitHub
- Make Dockerfile for each service repo
  - Install required Ruby
  - Install required gems
  - Copy the app
  etc

Note that in Production filebeat container can't no longer read ./log/app.log container.
so we have to modify our sinatra logger to output to STDOUT.
filebeat knows how to read STDOUT of other containers.

The instructions of those YML files are very tedious.
I'm not making notes.
They need to be written depending on situation.

Todo: make homework on Ansible.
