# py_env

Role py_env automates creation, package management, and removal of Python virtual environments

## Table of contents

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [py_env_actions](#py_env_actions)
  - [py_env_interpreter](#py_env_interpreter)
  - [py_env_list](#py_env_list)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.20`

## Default Variables

### py_env_actions

List of actions the role does, accepts one or more actions.
Use comma without spaces as a delimiter for multiple actions.

**_Required:_** `true`<br />
**_Type:_** String<br />

#### Example usage

```YAML
  py_env_actions: deploy_envs
```

### py_env_interpreter

Python interpreter used to create virtual environments

**_Type:_** String<br />

#### Default value

```YAML
py_env_interpreter: /usr/bin/python3
```

### py_env_list

Mapping of virtual environment paths to their configuration.
Each key is the absolute path for the venv; state defaults to present.

**_Required:_** `true`, only in case `py_env_actions: deploy_envs`<br />
**_Type:_** Dict<br />

#### Example usage

```YAML
py_env_list:
  /opt/myapp/venv:
    state: present
    packages:
      - name: requests
        state: present
      - name: flask
        state: present
  /opt/oldapp/venv:
    state: absent
```

## Dependencies

None.

## License

MIT

## Author

freedform
