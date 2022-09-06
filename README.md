# pyjapi - Python JAPI Client

## Getting Started

```sh
git clone git@git01.iis.fhg.de:ks-ip-lib/software/pyjapi.git
pip3 install -e pyjapi/.
```

## Usage

`japi [--host HOSTNAME] [--port N] [--format FORMAT_NAME] [-v] (list|listen|request)`

## Examples

### Issue individual JAPI commands

- `japi request <JAPI_COMMAND>`

    ```console
    $ japi request get_temperature
    temperature=27.0
    unit=celsius
    ```

- `japi request <COMMAND> [PARAMETERS]`

    ```console
    $ japi_pushsrv_subscribe service=push_temperature
    temperature=17.0
    unit=celsius
    ```

### List available push services

- `japi list`

    ```console
    $ japi list                                                                           -2-
    < japi_pushsrv_list(services=["push_temperature"])
    ```

### Listen to JAPI push services

- `japi listen <PUSH_SERVICE_NAME> <N_PACKAGES>`

    ```console
    $ japi listen push_temperature 3
    < push_temperature(temperature=24.833269096274833)
    < push_temperature(temperature=25.414709848078964)
    < push_temperature(temperature=25.912073600614352)
    ```
