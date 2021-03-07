[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/H2H43P9OI)

# Ansible role: valheim

Use LinuxGSM to install and configure a Valheim multiplayer dedicated server.

This role will create a new, unprivileged user and group in order to run a
Valheim dedicated server. Additionally, this role also manages firewall ports
for the server.

## Dependencies

* [stonesoupkitchen.linuxgsm](https://github.com/StoneSoupKitchen/ansible-role-linuxgsm)

## Example Playbook

To set up a new Valheim server:

    - hosts: servers
      roles:
         - stonesoupkitchen.valheim

To customize the default settings:

    - hosts: servers
      roles:
         - stonesoupkitchen.valheim
      vars:
        valheim_server_name: "Ansible Vikings!"
        valheim_server_password: "meadfordays"

## Role Variables

### Defaults

| Variable                   | Description                                      | Default            |
|----------------------------|--------------------------------------------------|--------------------|
| `valheim_install_dir`      | Default installation directory for Valheim.      | `/opt/valheim`     |
| `valheim_server_name`      | Display name of the server in the browser.       | `"Valheim Server"` |
| `valheim_server_password`  | Password users must enter to connect.            | `""`               |
| `valheim_server_port`      | Port the Valheim server will listen on.          | `2456`             |
| `valheim_server_gameworld` | Name of the world the server loads / generates.  | `"dedicated"`      |
| `valheim_server_public`    | 1 for public games over the internet. 0 for LAN. | `1` (public)       |

### Vars

| Variable        | Description                      |
|-----------------|----------------------------------|
| `valheim_user`  | The Valheim server user.         |
| `valheim_group` | The Valheim server user's group. |

## License

See [LICENSE](LICENSE).

