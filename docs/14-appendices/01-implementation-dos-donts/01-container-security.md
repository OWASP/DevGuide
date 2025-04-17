### 12.1.1 Container security

This is a collection of Do's and Don'ts when it comes to container security, gathered from practical experiences.
Some of these are language specific and others have more general applicability.

Container image security, host security, client security, daemon security, runtime security:

* Choose the right base image
* Include only the required packages in the image
* If using Docker images, use multi-stage builds
* Use layer caching and multi stage builds to:
  * Separate build-time dependencies from runtime dependencies
  * Remove special permissions from images
  * `find / -perm /6000 -type f -exec ls -ld {} \;`
  * RUN `find / -xdev -perm /6000 -type f -exec chmod a-s {} \; || true`
* Reduce overall image size by shipping only what your app needs to run,
    see the [Docker documentation][docker] for more information
* Remove unused images with prune: `docker image prune [OPTIONS]`
* Do not embed any secrets, passwords, keys, credentials, etc in images
* Use a read-only file system
* Sign images with cryptographic keys and not with username/password combination
* Secure your code and its dependencies
* Test your images for vulnerabilities
* Monitor container runtimes
* Docker Content Trust (DCT) is enabled on Docker clients
* Check freshness security of images with the provided timestamp key that is associated with the registry.
* Create the timestamp key by Docker and store on the server
* Use tagging keys associated with a registry.
    Such that a poisoned image from a different registry cannot be pushed into a registry.
* Use offline keys to sign the tagging keys.
* Offline keys are owned by the organization and secured in an out-of-band location.
* Scan images frequently for any vulnerabilities. Rebuilt all images to include patches
    and instantiate new containers from them
* Remove `setuid` and `setgid` permissions from the images.
* Where applicable, use 'copy' instruction in place of 'add' instruction.
* Verify authenticity of packages before installing them into images
* Use namespaces and control groups for containers
* Use bridge interfaces for the host
* Authenticity of packages is verified before installing them into images
* Mount files on a separate partition to address any situation where the mount becomes full,
    but the host still remains usable
* Mark registries as private and only use signed images.
* Pass commands through the authorization plugin to ensure that only authorized client connects to the daemon
* TLS authentication is configured to restrict access to the Docker daemon
* Namespaces are enabled to ensure that
* Leave control groups (cgroups) at default setting to ensure that tampering does not take place
    with excessive resource consumption.
* Do not enable experimental features for Docker
* set docker.service file ownership to root:root.
* Set docker.service file permissions to either 644 or to a more restrictive value.
* Set docker.socket file ownership and group ownership to root.
* Set file permissions on the docker.socket file to 644 or more restrictively
* Set /etc/docker directory ownership and group ownership to root
* Set /etc/docker directory permissions to 755 or more restrictively
* Set ownership of registry certificate files (usually found under `/etc/docker/certs.d/<registry-name>` directory)
    to individual ownership and is group owned by root.
* Set registry certificate files (usually found under `/etc/docker/certs.d/<registry-name>` directory)
    permissions to 444 or more restrictively.
* Acquire and ship daemon logs to SIEM for monitoring
* Inter-container network connections are restricted and enabled on a requirement basis.
    By default containers cannot capture packets that have other containers as destination
* Where hairpin NAT is enabled, userland proxy is disabled
* Docker daemon is run as a non-root user to mitigate lateral privilege escalation
    due to any possible compromise of vulnerabilities.
* `No_new_priv` is set (but not to false) to ensure that containers cannot gain additional privileges
    via `suid` or `sgid`
* Default SECCOMP profile is applied for access control.
* TLS CA certificate file on the image host (the file that is passed along with the `--tlscacert` parameter)
    is individually owned and group owned by root
* TLS CA certificate file on the image host (the file that is passed along with the `--tlscacert` parameter)
    has permissions of 444 or is set more restrictively
* Containers should run as a non-root user.
* Containers should have as small a footprint as possible, and should not contain unnecessary software packages
    which could increase their attack surface
* Docker default bridge 'docker0' is not used to avoid ARP spoofing and MAC flooding attacks
* Either Dockers AppArmor policy is enabled or the Docker hosts AppArmor is enabled.
* SELinux policy is enabled on the Docker host.
* Linux kernel capabilities are restricted within containers
* privileged containers are not used
* sensitive host system directories are not mounted on containers
* `sshd` is not run within containers
* privileged ports are not mapped within containers (TCP/IP port numbers below 1024 are considered privileged ports)
* only needed ports are open on the container.
* the hosts network namespace is not shared.
* containers root filesystem is mounted as read only
* Do not use docker exec with the `--privileged` option.
* docker exec commands are not used with the user=root option
* cgroup usage is confirmed
* The `no_new_priv` option prevents LSMs like SELinux from allowing processes to acquire new privileges
* Docker socket is not mounted inside any containers to prevent processes running within the container
    to execute Docker commands which would effectively allow for full control of the host.
* incoming container traffic is bound to a specific host interface
* hosts process namespace is not shared to ensure that processes are separated
* hosts IPC namespace is not shared to ensure that inter-process communications does not take place
* host devices are not directly exposed to containers
* hosts user namespaces are not shared to ensure isolation of containers
* CPU priority is set appropriately on containers
* memory usage for containers is limited.
* 'on-failure' container restart policy is set to '5'
* default `ulimit` is overwritten at runtime if needed
* container health is checked at runtime
* PIDs cgroup limit is used (limit is set as applicable)
* The Docker host is hardened to ensure that only Docker services are run on the host
* Secure configurations are applied to ensure that the containers do not gain access to the host via the Docker daemon
* Docker is updated with the latest patches such that vulnerabilities are not compromised
* The underlying host is managed to ensure that vulnerabilities are identified and mitigated with patches
* Docker server certificate file (the file that is passed along with the `--tlscert` parameter)
    is individual owned and group owned by root.
* Docker server certificate file (the file that is passed along with the `--tlscert` parameter)
    has permissions of 444 or more restrictive permissions.
* Docker server certificate key file (the file that is passed along with the `--tlskey` parameter)
    is individually owned and group owned by root.
* Docker server certificate key file (the file that is passed along with the `--tlskey` parameter) has permissions of 400
* Docker socket file is owned by root and group owned by docker.
* Docker socket file has permissions of 660 or are configured more restrictively
* ensure `daemon.json` file individual ownership and group ownership is correctly set to root, if it is in use
* if `daemon.json` file is present its file permissions are correctly set to 644 or more restrictively

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140101] or [edit on GitHub][edit140101].

[docker]: https://docs.docker.com/get-started/09_image_best/
[edit140101]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/14-appendices/01-implementation-dos-donts/01-container-security.md
[issue140101]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%20/14-appendices/01-implementation-dos-donts/01-container-security
