---
title: "Config"
hide_table_of_contents: true
sidebar_position: 9
---


# <kbd>module</kbd> `config`




**Global Variables**
---------------
- **default**
- **local**
- **testnet**
- **mainnet**
- **DEFAULT_DOCKER_LABEL**
- **DEFAULT_FILTER**
- **MAX_STATUS_SIZE**

---


## <kbd>function</kbd> `get_config`

```python
get_config(key, _dict)
```






---


## <kbd>function</kbd> `load_config`

```python
load_config(location: str, name: str) → Dict[str, Dict]
```






---


## <kbd>function</kbd> `build_docker_manifest`

```python
build_docker_manifest(config: Dict) → List[str]
```






---


## <kbd>function</kbd> `check_docker_manifest`

```python
check_docker_manifest(client, manifest: List)
```






---


## <kbd>function</kbd> `randomize_conf_ports`

```python
randomize_conf_ports(config: Dict) → Dict
```






---


## <kbd>function</kbd> `randomize_conf_creds`

```python
randomize_conf_creds(config: Dict) → Dict
```






---


## <kbd>function</kbd> `add_virtual_networking`

```python
add_virtual_networking(config: Dict) → Dict
```








---

_This file was automatically generated via [lazydocs](https://github.com/ml-tooling/lazydocs)._
