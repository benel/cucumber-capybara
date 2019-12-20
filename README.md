# Cucumber and Capybara for Docker
(with Cuprite and Google Chrome)

## Prerequisites 

* Docker

## Install

```sh
docker pull benel/cucumber-capybara
```

## Use 

* Initializing Cucumber in the current directory

```shell
docker run --rm -v "$(pwd)":/app cucumber-capybara --init
```

* Generating skeleton steps from scenarios (with color highlights)

```shell
docker run --rm -v "$(pwd)":/app -t cucumber-capybara
```

* Testing implemented scenarios on a given service and retry on failure 
(the environment variable must be used in capybara scripts)

```shell
docker run --rm -v "$(pwd)":/app -t --net="host" --env APP_HOST="http://10.10.10.118:3000" benel/cucumber-capybara --retry 3
```
