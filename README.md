# ansible-role-win-remotedesktopgateway

Role to install Windows Remote Desktop Gateway Server and provide CAP and RAP

## Table of content

- [Default Variables](#default-variables)
  - [win_rdg_install_management_tools](#win_rdg_install_management_tools)
  - [win_rdg_install_rdweb](#win_rdg_install_rdweb)
  - [win_rdg_rds_cap_allow_only_sdrts_servers](#win_rdg_rds_cap_allow_only_sdrts_servers)
  - [win_rdg_rds_cap_auth_method](#win_rdg_rds_cap_auth_method)
  - [win_rdg_rds_cap_computer_groups](#win_rdg_rds_cap_computer_groups)
  - [win_rdg_rds_cap_idle_timeout](#win_rdg_rds_cap_idle_timeout)
  - [win_rdg_rds_cap_name](#win_rdg_rds_cap_name)
  - [win_rdg_rds_cap_redirect_clipboard](#win_rdg_rds_cap_redirect_clipboard)
  - [win_rdg_rds_cap_redirect_drives](#win_rdg_rds_cap_redirect_drives)
  - [win_rdg_rds_cap_redirect_pnp](#win_rdg_rds_cap_redirect_pnp)
  - [win_rdg_rds_cap_redirect_printers](#win_rdg_rds_cap_redirect_printers)
  - [win_rdg_rds_cap_redirect_serial](#win_rdg_rds_cap_redirect_serial)
  - [win_rdg_rds_cap_session_timeout](#win_rdg_rds_cap_session_timeout)
  - [win_rdg_rds_cap_session_timeout_action](#win_rdg_rds_cap_session_timeout_action)
  - [win_rdg_rds_cap_state](#win_rdg_rds_cap_state)
  - [win_rdg_rds_cap_user_groups](#win_rdg_rds_cap_user_groups)
  - [win_rdg_rds_rap_allowed_ports](#win_rdg_rds_rap_allowed_ports)
  - [win_rdg_rds_rap_computer_group](#win_rdg_rds_rap_computer_group)
  - [win_rdg_rds_rap_computer_group_type](#win_rdg_rds_rap_computer_group_type)
  - [win_rdg_rds_rap_description](#win_rdg_rds_rap_description)
  - [win_rdg_rds_rap_name](#win_rdg_rds_rap_name)
  - [win_rdg_rds_rap_state](#win_rdg_rds_rap_state)
  - [win_rdg_rds_rap_user_groups](#win_rdg_rds_rap_user_groups)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### win_rdg_install_management_tools

Install Windows Remote Desktop Gateway Management Tools

#### Default value

```YAML
win_rdg_install_management_tools: true
```

### win_rdg_install_rdweb

Install Windows Remote Desktop Web Access Role

#### Default value

```YAML
win_rdg_install_rdweb: false
```

### win_rdg_rds_cap_allow_only_sdrts_servers

Specifies whether connections are allowed only to Remote Desktop Session Host servers that enforce Remote Desktop Gateway redirection policy.

#### Default value

```YAML
win_rdg_rds_cap_allow_only_sdrts_servers: no
```

### win_rdg_rds_cap_auth_method

Specifies how the RD Gateway server authenticates users. When a new CAP is created, the default value is password. Options: both, none, password, smartcard

#### Default value

```YAML
win_rdg_rds_cap_auth_method: password
```

### win_rdg_rds_cap_computer_groups

A list of computer groups that is allowed to connect to the Remote Gateway server.

#### Default value

```YAML
win_rdg_rds_cap_computer_groups: []
```

### win_rdg_rds_cap_idle_timeout

Specifies the time interval, in minutes, after which an idle session is disconnected. A value of zero disables idle timeout.

#### Default value

```YAML
win_rdg_rds_cap_idle_timeout: 0
```

### win_rdg_rds_cap_name

Name of the connection authorization policy.

#### Default value

```YAML
win_rdg_rds_cap_name: RDS_CAP
```

### win_rdg_rds_cap_redirect_clipboard

Allow clipboard redirection.

#### Default value

```YAML
win_rdg_rds_cap_redirect_clipboard: yes
```

### win_rdg_rds_cap_redirect_drives

Allow disk drive redirection.

#### Default value

```YAML
win_rdg_rds_cap_redirect_drives: yes
```

### win_rdg_rds_cap_redirect_pnp

Allow Plug and Play devices redirection.

#### Default value

```YAML
win_rdg_rds_cap_redirect_pnp: no
```

### win_rdg_rds_cap_redirect_printers

Allow printers redirection.

#### Default value

```YAML
win_rdg_rds_cap_redirect_printers: no
```

### win_rdg_rds_cap_redirect_serial

Allow serial port redirection.

#### Default value

```YAML
win_rdg_rds_cap_redirect_serial: no
```

### win_rdg_rds_cap_session_timeout

The maximum time, in minutes, that a session can be idle. A value of zero disables session timeout.

#### Default value

```YAML
win_rdg_rds_cap_session_timeout: 0
```

### win_rdg_rds_cap_session_timeout_action

The action the server takes when a session times out. disconnect: disconnect the session. reauth: silently reauthenticate and reauthorize the session.

#### Default value

```YAML
win_rdg_rds_cap_session_timeout_action: disconnect
```

### win_rdg_rds_cap_state

The state of connection authorization policy. If `absent` will ensure the policy is removed. If `present` will ensure the policy is configured and exists. If `enabled` will ensure the policy is configured, exists and enabled. If `disabled` will ensure the policy is configured, exists, but disabled.

#### Default value

```YAML
win_rdg_rds_cap_state: enabled
```

### win_rdg_rds_cap_user_groups

A list of user groups that is allowed to connect to the Remote Gateway server. Required when a new CAP is created.

#### Default value

```YAML
win_rdg_rds_cap_user_groups: []
```

### win_rdg_rds_rap_allowed_ports

List of port numbers through which connections are allowed for this policy. To allow connections through any port, specify ‘any’.

#### Default value

```YAML
win_rdg_rds_rap_allowed_ports:
  - any
```

### win_rdg_rds_rap_computer_group

The computer group name that is associated with this resource authorization policy (RAP). This is required when computer_group_type is rdg_group or ad_network_resource_group.

### win_rdg_rds_rap_computer_group_type

The computer group type: `rdg_group`: RD Gateway-managed group `ad_network_resource_group`: Active Directory Domain Services network resource group `allow_any`: Allow users to connect to any network resource.

#### Default value

```YAML
win_rdg_rds_rap_computer_group_type: allow_any
```

### win_rdg_rds_rap_description

Optional description of the resource authorization policy.

#### Default value

```YAML
win_rdg_rds_rap_description: Allow all users to connect to any resource
```

### win_rdg_rds_rap_name

Name of the resource authorization policy.

#### Default value

```YAML
win_rdg_rds_rap_name: RDS_RAP
```

### win_rdg_rds_rap_state

The state of resource authorization policy. If `absent` will ensure the policy is removed. If `present` will ensure the policy is configured and exists. If `enabled` will ensure the policy is configured, exists and enabled. If `disabled` will ensure the policy is configured, exists, but disabled.

#### Default value

```YAML
win_rdg_rds_rap_state: enabled
```

### win_rdg_rds_rap_user_groups

List of user groups that are associated with this resource authorization policy (RAP). A user must belong to one of these groups to access the RD Gateway server. Required when a new RAP is created.

#### Default value

```YAML
win_rdg_rds_rap_user_groups: []
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
