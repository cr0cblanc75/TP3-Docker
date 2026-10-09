Base command to connect with the SSH (without using setup.yml)
```bash
ssh -i id_rsa  admin@eugene.lallain.takima.school
```

## 3-1 Question

Now that we have a `setup.yml` we can directly use this command.

```bash
ansible all -i ansible/inventories/setup.yml -m ping
```

### Question
Not necessarily. Several risks exist:
- Malicious images: if an attacker compromises a developer's Docker Hub account, they could publish a malicious image that would automatically be deployed to the server.
- Vulnerable images: a new image may contain known security vulnerabilities or outdated dependencies.
- Broken deployments: a new image may introduce bugs, break compatibility with the database, or cause the application to stop working.
- Supply chain attacks: an image or one of its dependencies could be compromised during the build or publication process.
- Uncontrolled changes: using the latest tag does not identify a specific image version. The same tag can point to different image contents over time, making deployments harder to reproduce and roll back.


### .env
```bash
set -a
source .env
set +a
```

