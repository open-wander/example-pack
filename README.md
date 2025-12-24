# hello_pack

This pack is a simple Nomad job that runs as a service and can be accessed via
HTTP.

## Pack Usage

### Changing the Message

To change the message this server responds with, change the "message" variable
when running the pack.

```bash
nomad-pack run hello_pack --var message="Hola Mundo!"
```

This tells Nomad Pack to tweak the `MESSAGE` environment variable that the
service reads from.

## Variables

| Variable | Description | Type | Default |
|Str|Str|Str|Str|
|---|---|---|---|
| `message` | The message your application will respond with | string | `"Hello World!"` |
| `count` | The number of app instances to deploy | number | `2` |
| `job_name` | The name to use as the job name which overrides using the pack name | string | `""` (Pack Name) |
| `datacenters` | A list of datacenters in the region which are eligible for task placement | list(string) | `["*"]` |
| `region` | The region where jobs will be deployed | string | `""` |
| `register_service` | If you want to register a Nomad service for the job | bool | `true` |
| `service_name` | The service name for the hello_pack application | string | `"webapp"` |
| `service_tags` | The service tags for the hello_pack application | list(string) | `["urlprefix-/", "traefik.enable=true", ...]` |

[pack-registry]: https://rmbl.openwander.org/