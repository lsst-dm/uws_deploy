# uws-api-server

Helm chart for deploying the Universal Worker Service API Server

**Homepage:** <https://github.com/lsst-dm/uws-api-server>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| basePath | string | `"uws-server"` | The base path for the client ingress |
| client.enabled | bool | `false` | Turn on the UWS client system if desired |
| hostname | string | `""` | Hostname for the client ingress |
| image.repository | string | `"lsstdm/uws-api-server"` | The Docker registry name of the UWS server container image |
| image.tag | string | `"latest"` | The tag of the UWS server container image |
| job.image.repository | string | `"lsstsqre/centos"` | The Docker registry name of the UWS job container image |
| job.image.tag | string | `"d_latest"` | The tag of the UWS job container image |
| job.securityContext.fsGroup | int | `202` | Set the filesystem GID for the mounted volumes in the UWS job container |
| job.securityContext.runAsGroup | int | `202` | Set the GID for the UWS job container entrypoint |
| job.securityContext.runAsUser | int | `1000` | Set the UID for the UWS job container entrypoint |
| logLevel | string | `"WARNING"` | Log level of server. Set to "DEBUG" for highest verbosity |
| replicaCount | int | `1` | Set the replica count for the UWS server |
| server.securityContext.fsGroup | int | `202` | Set the filesystem GID for the mounted volumes in the UWS server container |
| server.securityContext.runAsGroup | int | `202` | Set the GID for the UWS server container entrypoint |
| server.securityContext.runAsUser | int | `1000` | Set the UID for the UWS server container entrypoint |
| targetCluster | string | `""` | Target Kubernetes cluster |
| volumes | list | `[]` | Central data volumes to be mounted in job containers. Each object listed can have the following attributes defined: _name_ (A label identifier for the data volume mount) _server_ (The hostname for the NFS server with the data volume mount) _claimName_ (The PVC claim name for the data volume mount) _mountPath_ (The mount path in the server container for the data volume mount) _exportPath_ (The export path on the NFS server for the data volume mount) _subPath_ (A possible sub path for the data volume mount) _readOnly_ (Flag to mark the data volume mount as read only or read/write) |
| workingVolume.claimName | string | `""` | The PVC claim name for the working volume |
| workingVolume.exportPath | string | `""` | The export path on the NFS server for the working volume |
| workingVolume.mountPath | string | `"/uws"` | The mount path in the server container for the working volume |
| workingVolume.name | string | `"job-files"` | A label identifier for the working volume |
| workingVolume.server | string | `""` | The hostname for the NFS server with the working volume |
| workingVolume.subPath | string | `""` | A possible sub path for the working volume mount |