# pretested-pr-workshop

working with automatically merged pull requests

## Setup

```
docker volume create jankees
docker run -d --name my-jenkins -p 8080:8080 -v jankees:/var/jenkins_home jenkins/jenkins:lts
docker logs my-jenkins
```

Don't install any plugins. Create admin account, go to plugin manager. Install

```
Pipeline
Pipeline: GitHub
GitHub Branch Source Plugin
OWASP Markup Formatter Plugin (Optional, but for niceties)
```

(You might want to restart jenkins after installing the plugins, it takes 10 sec.. I "think" Pipeline: GitHub needs the restart..)

Go to `Jenkins -> New Item -> GitHub Organization`, configure `GitHub Organization`
- `Credentials` (you _might_ want to create a bot-account w/ read access to the org)
- `Owner` name of the organization on GitHub
- `Behaviours` only keep "Discover pull requests from origin" - investigate Stragegies
