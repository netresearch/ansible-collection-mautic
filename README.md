# Ansible Collection - netresearch.mautic

## Description

This collection provides setting up and updating a Docker based Mautic stack.

## Included Content

- [mautic](roles/mautic/)

## Installation

Install the collection via ansible-galaxy:

`ansible-galaxy collection install netresearch.mautic`

You can also include the collection in a `requirements.yml` file and install it via `ansible-galaxy collection install -r requirements.yml`, using the format:

```yaml
---
collections:
  - name: netresearch.mautic
    version: 1.0.0
```

## Using this collection

Please refer to the examples in the readmes of the role.

See [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.
