---
title: "Management Tips"
hide_table_of_contents: true
sidebar_position: 3
---

# Management Tips

## Repair broken data

In case of `dirty database replay required` situation in `nodeos`, you can use
the new `tevmc repair` command, this command will trim elastic data to latest
valid block, then download a `nodeos` snapshot close to that block, it will
tweak the `tevmc.json` file to start from it on next run.

## Daemon API

The `tevmc` daemon serves an administration API at port `12321` by default, here
are some useful `curl` commands:

### Restart container

To restart only a specific container just do:

```bash
curl -X POST \
    -H 'Content-Type: application/json' \
    -d '{"service": "rpc"}' \
    http://localhost:12321/restart
```

Replace `rpc` with the service you want, can be one of: `nodeos`, `indexer` & `rpc`.

### Update in place

Same API as `/restart` but need to also pass: `"update": true` in the data, this will
force a rebuild of the docker image before relaunch.

```bash
curl -X POST \
    -H 'Content-Type: application/json' \
    -d '{"service": "rpc", "update": true}' \
    http://localhost:12321/restart
```

### Data integrity Check

This API runs several queries against `elastic` data to check for gaps in blocks, or
duplicated documents.

`curl -X GET http://localhost:12321/check`
