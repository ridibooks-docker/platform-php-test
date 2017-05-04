# platform-php-test
Docker image for platform team

## Supported Docker Images

* ridibooks/platform-php-test:7.0 ([Dockerfile](https://github.com/ridibooks-docker/platform-php-test/blob/master/7.0/Dockerfile))

## Test with Gitlab Runner

1. Download and install [gitlab-ci-multi-runner](https://gitlab.com/gitlab-org/gitlab-ci-multi-runner)
2. Go to the project's directory that has `.gitlab-ci.yml` file.
3. Run `gitlab-runner exec ...` command like below:

```
# without SSH key
gitlab-runner exec docker [task_name]

# with SSH key
gitlab-runner exec docker [task_name] --env SSH_PRIVATE_KEY="`cat ~/.ssh/id_rsa`"
```
