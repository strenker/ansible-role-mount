mount
=====

Simple version of Linix mount(8) command.

Role Variables
--------------

__**mount_src:**__

Source path of what will me mounted.<br>
Relative path names are relative to `remote_user`

__**mount_mountpoint:**__

Destination directory where to be mounted. The directory must exist.<br>
Relative path names are relative to ansible_user.

__**mount_options:**__

__Optional:__ options to the mount command.<br>
Please ommit the '-o'.<br>
__Default:__ ''

__**mount_may_fail:**__

__Optional:__
- `true`: mount(8) does not fail if `mount_src` is already mounted to `mount_mountpoint`<br>
- `false`: default behavior of mount(8)<br>
__Default:__ false

__**___mount_other_errors:** Please do not change__

For completeness: mount(8) result codes other than 0 or 1.

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