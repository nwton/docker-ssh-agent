# Jenkins SSH Build Agent Docker image

[![Docker Stars](https://img.shields.io/docker/stars/jenkins/ssh-build-agent.svg)](https://hub.docker.com/r/jenkins/ssh-build-agent/)
[![Docker Pulls](https://img.shields.io/docker/pulls/jenkins/ssh-build-agent.svg)](https://hub.docker.com/r/jenkins/ssh-build-agent/)
[![GitHub release](https://img.shields.io/github/release/jenkinsci/docker-ssh-build-agent.svg?label=changelog)](https://github.com/jenkinsci/docker-ssh-build-agent/releases)

A [Jenkins](https://jenkins.io) agent using SSH to establish connection.

See [Jenkins Distributed builds](https://wiki.jenkins-ci.org/display/JENKINS/Distributed+builds) for more info.

## Running

To run a Docker container

```bash
docker run jenkins/ssh-build-agent "<public key>"
```

You'll then be able to connect this agent using the [SSH Build Agents plugin](https://plugins.jenkins.io/ssh-slaves) as "jenkins" with the matching private key.

### How to use this image with Docker Plugin

To use this image with [Docker Plugin](https://plugins.jenkins.io/docker), you need to
pass the public SSH key using environment variable `JENKINS_AGENT_SSH_PUBKEY` and not as a startup argument.

In _Environment_ field of the Docker Template (advanced section), just add:

    JENKINS_AGENT_SSH_PUBKEY=<YOUR PUBLIC SSH KEY HERE>

Don't put quotes around the public key. You should be all set.

## Changelog

See [GitHub Releases](https://github.com/jenkinsci/docker-ssh-build-agent/releases/latest).
Note that the changelogs and release tags were introduced in Dec 2019, and there is no entries for previous patches.
Please consult with the commit history if needed.
