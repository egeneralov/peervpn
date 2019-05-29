egeneralov.peervpn
==================

Role Variables
--------------

See [official config file](https://raw.githubusercontent.com/peervpn/peervpn/master/peervpn.conf) for option descriprion.

- **networks**: list with dicts
  - **networkname**: string `PEERVPN`
    **psk**: string `mytopsecretpassword`
    **net**: Subnet for distribution between your hosts `192.168.1.0/30`
    **state**: define `absent` for delete network
    **port**: int `7000`
    **enabletunneling**: boolean in string, use quotes, please `"yes"`
    **interface**: string `tap0`
    **upcmd**: string for /bin/sh `echo virtual interface is up`
    **local**: bind to `0.0.0.0`
    **sockmark**: define more than 0 to mark packets `0`
    **enableipv4**: boolean in string, use quotes, please `"yes"`
    **enableipv6**: : boolean in string, use quotes, please `"no"`
    **enablenat64clat**: boolean in string, use quotes, please `"no"`
    **enablendpcache**: : boolean in string, use quotes, please `"no"`
    **enablerelay**: : boolean in string, use quotes, please `"yes"`
    **engine**: string `padlock`
    **enableprivdrop**: : boolean in string, use quotes, please `"no"`
    **user**: `nobody`
    **group**: `nogroup`
    **chroot**: `/var/empty`

Example Playbook
----------------

**WARNING**: The use of the group name "peervpn" is mandatory.

    - hosts: peervpn
      networks:
        - networkname: PEERVPN
          psk: mytopsecretpassword
          # state: absent
          port: 7000
          enabletunneling: "yes"
          interface: "tap0"
          net: "192.168.1.0/30"
      roles:
         - egeneralov.peervpn


License
-------

MIT

Author Information
------------------

Eduard Generalov <eduard@generalov.net>
