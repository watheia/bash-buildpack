# Bash Process Buildpack

A buildpack whose intent is to show how processes work. This buildpack adds a `sys-info` process which displays
information about it's runtime environment.

## Usage

### Build

```bash
pack build sample-bash-app --builder dapper-devops/slim-builder:latest  --buildpack ../java-maven --buildpack . --path ../../examples/java-maven
```

OR

```bash
pack build sample-bash-app --builder dapper-devops/slim-builder:bionic --buildpack ../java-maven --buildpack . --path ../../examples/java-maven
```

### Run

```bash
# System info
docker run --env CNB_PROCESS_TYPE=sys-info -it sample-bash-app

# Web server
docker run --env CNB_PROCESS_TYPE=web -it -p 8080:8080 sample-bash-app

# Web server (slim)
docker run -it -p 8080:8080 sample-bash-app
```
