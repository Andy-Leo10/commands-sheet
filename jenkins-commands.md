# Jenkins

- [Jenkins](#jenkins)
  - [For installation:](#for-installation)
  - [For checking available commands:](#for-checking-available-commands)
  - [For running a job:](#for-running-a-job)
  - [For aborting a job:](#for-aborting-a-job)
  - [For cleaning history of a job:](#for-cleaning-history-of-a-job)

## For installation:
PENDING!!!!!!!!!!!!!!!!!!!!!!!

> First of all:
> ```
> cd /WHERE_JENKINS_CLI_IS_LOCATED
> ```

## For checking available commands:
```
java -jar jenkins-cli.jar -s http://localhost:8080/ -auth @.jenkins_cli help
```

## For running a job:
```
java -jar jenkins-cli.jar -s http://localhost:8080/ -auth @.jenkins_cli build <JOB_NAME> -f -s -v
```

## For aborting a job:
```
java -jar jenkins-cli.jar -s http://localhost:8080/ -auth @.jenkins_cli stop-builds <JOB_NAME>
```

## For cleaning history of a job:
```
java -jar jenkins-cli.jar -s http://localhost:8080/ -auth @.jenkins_cli delete-builds <JOB_NAME> <BUILD_NUMBER>
```