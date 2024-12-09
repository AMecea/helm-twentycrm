# TwentyCRM helm chart


This repository provides a helm chart to deploy TwentyCRM.

## Install

Create a `values.yaml` file and put all your config, see `Configuration` section, then run:

```
helm repo add amecea https://amecea.github.io/helm-twentycrm
helm upgrade -i twenty-crm amecea/twentycrm -f values.yaml
```

## Configuration

For a complete list of configuration fields please check [values.yaml](./values.yaml) file.


| Field Name                       | Description                                                                               | Default Value           |
|----------------------------------|-------------------------------------------------------------------------------------------|-------------------------|
| `image`                          | Docker image for the application.                                                        | `twentycrm/twenty:latest` |
| `env`                            | List of environment variables for configuring the application.                           | `[]`                    |
| `secrets.accessToken`            | Access token for authentication.                                                         |                         |
| `secrets.loginToken`             | Login token for authentication.                                                          |                         |
| `secrets.refreshToken`           | Refresh token for authentication.                                                        |                         |
| `secrets.fileToken`              | File token for authentication.                                                           |                         |
| `server.replicas`                | Number of server replicas.                                                               | `1`                     |
| `server.storage`                 | Storage size for the server.                                                             | `5Gi`                   |
| `server.storageClassName`        | Storage class name for server persistence.                                               |                         |
| `server.resources.requests.memory` | Memory resource request for the server.                                                 | `128Mi`                 |
| `server.resources.requests.cpu`  | CPU resource request for the server.                                                    | `100m`                  |
| `worker.replicas`                | Number of worker replicas.                                                               | `1`                     |
| `worker.resources.requests.memory` | Memory resource request for workers.                                                   | `128Mi`                 |
| `worker.resources.requests.cpu`  | CPU resource request for workers.                                                       | `100m`                  |
| `db.image`                       | Docker image for the PostgreSQL database.                                                | `twentycrm/twenty-postgres:latest` |
| `db.storage`                     | Storage size for the database.                                                           | `5Gi`                   |
| `db.storageClassName`            | Storage class name for database persistence.                                             |                         |
| `db.adminPassword`               | Admin password for the database.                                                        |                         |
| `db.database`                    | Name of the database.                                                                    | `twenty`                |
| `db.user`                        | Database user name.                                                                      | `twenty`                |
| `db.password`                    | Password for the database user.                                                         | `twenty`                |
| `db.resources.requests.memory`   | Memory resource request for the database.                                               | `256Mi`                 |
| `db.resources.requests.cpu`      | CPU resource request for the database.                                                  | `100m`                  |
| `redis.image`                    | Docker image for Redis.                                                                  | `redis:latest`          |
| `redis.resources.requests.memory` | Memory resource request for Redis.                                                     | `128Mi`                 |
| `redis.resources.requests.cpu`   | CPU resource request for Redis.                                                         | `20m`                   |
| `ingress.enabled`                | Enable or disable ingress.                                                              | `true`                  |
| `ingress.host`                   | Hostname for the ingress.                                                               | `crm.example.com`       |
| `ingress.class`                  | Ingress class name.                                                                      | `nginx`                 |

