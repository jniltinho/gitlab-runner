# gitlab-runner
gitlab-runner - With automatic import from CA( registry docker and gitlab server )

## Usage
  0. Fork and clone
  1. Create .env file (root directory)
  2. You can put variables in the .env file:

```
    REGISTRY_ADDRESS=reg.acme.com
    REGISTRY_PORT=5000
    GITLAB_ADDRESS=git.acme.com
    GITLAB_PORT=443
```
  3. Run make... :)


# WARNING!!!!
```
concurrent = 1
check_interval = 0
[[runners]]
  name = "example-docker"
  url = "https://git.acme.com/"
  token = "XXXXXXXX"
  executor = "docker"
  tls-skip-verify = true
  environment = ['GIT_SSL_NO_VERIFY=true']
  [runners.docker]
    tls_verify = false
    image = "docker:latest"
    privileged = true
    disable_cache = false
    volumes = ["/var/run/docker.sock:/var/run/docker.sock", "/cache"]
    shm_size = 0
```
