# Mautic Ansible Role

This Ansible role provides a marketing automation tool called "Mautic" via Docker

Currently supported platforms:

- Debian 10 and 11

What does this role do?

- Configures and provisions a Mautic service stack

## Requirements

Docker on target systems

## Configuration

Most important configuration options are as follows:

| Name                              | Default Value                 | Description                                     |
|-----------------------------------|-------------------------------|-------------------------------------------------|
| `mautic_site_url`                 | `http://mautic.local:80/`     | Mautic site URL                                 |
| `mautic_instance_name`            | `mautic`                      | Mautic instance stack prefix/identifier         |
| `mautic_db_root_secret`           | `my_secret`                   | Database root password                          |
| `mautic_db_user_secret`           | `my_secret`                   | Database user password                          |
| `mautic_network_frontend`         | `traefik_dev_network`         | Frontend network attached to httpd service      |
| `mautic_app_image_name`           | `ghcr.io/netresearch/mautic`  | Mautic container image name                     |
| `mautic_app_image_tag`            | `4.2-php7.4`                  | Mautic container image tag                      |
| `mautic_setup_force_log`          | `false`                       | Enables output of log even for sensitive data   |
| `mautic_trusted_proxies`          | `["127.0.0.1"]`               | Trusted proxies to detect client IP address     |
| `mautic_app_env`                  | see defaults/main.yml         | Passed ENV variables, f.e. Mautic configuration |

see `defaults/main.yml` for more configuration options.

## Tags

mautic-setup-all
: Run all tasks to set up Mautic on target system. These are also the tasks which will run if tags are provided. It ensures Mautic is properly set up on target system.

mautic-update
: Run Mautic CLI commands to update itself in place. This tag should be run regularly to ensure all components are up to date - not only Mautic itself but also RTE, DBMS, base OS and all it's libraries.

mautic-prepare-host
: Prepare target host for Mautic. Included in `mautic-setup-all`.

mautic-network
: Configure Docker network for Mautic. Included in `mautic-setup-all`.

mautic-start-db
: Configure and start database service. Included in `mautic-setup-all`.

mautic-start-service
: Just run tasks to start Docker container. Included in `mautic-setup-all`.

mautic-uninstall
: Remove all service containers.

mautic-prune
: Prune all volumes.
