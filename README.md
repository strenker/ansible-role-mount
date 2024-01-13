mount
=====

Simple version of Linux **`mount(8)`** command.

Role Variables
--------------

_**mount_src:**_

Source path of what will me mounted.<br>
Relative path names are relative to `remote_user`

_**mount_mountpoint:**_

Destination directory where to be mounted. The directory must exist.<br>
Relative path names are relative to ansible_user.

_**mount_options:**_

_Optional:_ options to the mount command.<br>
Please ommit the '-o'.<br>
_Default:_ ''

_**mount_may_fail:**_

_Optional:_
- `true`: `mount(8)` does not fail if `mount_src` is already mounted to `mount_mountpoint`<br>
- `false`: default behavior of `mount(8)`<br>

_Default:_ `false`

_**___mount_other_errors:** Please do not change_

For completeness: `mount(8)` result codes other than 0 or 1.

Example Playbook
----------------

This example mounts an ISO-File read-only and it does not bail out, if the file is already mounted 

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      remote_user: root
      roles:
        - { role: mount, mount_src: "Absolute path to File", mount_mountpoint: "/mnt/iso", mount_options: "ro,loop", mount_may_fail: true }

License
-------

GPLv3

Author Information
------------------

Stefan Trenker<br>
E-Mail: strenker63 at gmail.com
