# [Catena](https://github.com/alysoid/catena) - Samba Ansible Role

Setup Samba as file server and manage [smb.conf](https://man.archlinux.org/man/smb.conf.5) - The configuration file for the Samba suite.

## Role variables

| Variable            | Default   | Info
| ----------------    | --------- | ----------------
| `samba_shares`      | `[]`      | List of dicts with shares definitions.

---

### `samba_shares`

Define a list of dicts with shares definitions that will be mounted by Samba:

```yaml
samba_shares:
  # Name of the shared resource
  - name: Storage
    # Unix dictionary of the share
    path: /mnt/storage
    # Space separated list of users allowed to login
    valid_users: "{{ samba_username }}"
    # Space separated list of users with read-write access
    write_list: "{{ samba_username }}"
    # Define if the share will be visible in the list of available shares
    browseable: 'yes'
    # Define if users can create or modify files in the directory
    writable: 'yes'
```
