mount
=====

Simple version of Linix mount(8) command.

Role Variables
--------------

mount_src:
  Source path of what will me mounted.
  Relative path names are relative to ansible_user

mount_mountpoint:
  Destination directory where to be mounted. The directory must exist.
  Relative path names are relative to ansible_user

mount_options:
  Optional: options to the mount command.
  Please ommit the '-o'
  Default: ''
  
mount_may_fail:
  Optional:
    - true: mount(8) does not fail if mount_src is already mounted to mount_mountpoin
    - false: default behavior of mount(8)
  Default: false

___mount_other_errors: _Please do not change_
  For completeness: mount(8) result codes other than 0 or 1

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

Stefan Trenker
E-Mail: strenker63@gmail.com