# Ansible Role: Java deployment

An Ansible Role that deploys an Java application on the Debian based server.


## Requirements

None.


## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Variable                    | Required | Default              | Comments                                |
| --------------------------- | -------- | -------------------- | --------------------------------------- |
| `deployment_artifact`       | *yes*    | `app.jar`            | Path to the compiled file               |
| `deployment_workdir`        | *no*     | `deployment_workdir` | Working directory                       |
| `deployment_user`           | *no*     | `root`               | UNIX user that the app is executed as   |
| `deployment_group`          | *no*     | `root`               | UNIX user that the app is executed as   |
| `deployment_spring_profile` | *yes*    | `development`        | Spring profile name                     |
| `deployment_server_port`    | *yes*    | `8080`               | Port number which the server listens to |
| `deployment_service`        | *no*     | `backend`            | Name of the systemd service             |


## Dependencies

None.


## Example Playbook

```yaml
- hosts: all
  become: true

  roles:
  - staketab.java-deployment
```
