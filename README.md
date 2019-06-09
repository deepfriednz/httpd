HTTPD
=========

Role to install a specified version of HTTPD onto CentOS 7.x server using an RPM. This includes requesting HAProxy to drain the connections before starting the install and then re-enabling it during clean up.

This role also adds a firewall rule to allow port 80 through firewalld.

This will re-install if http_version and the current version installed are the same.

Requirements
------------

Ansible 2.6 <

Role Variables
--------------

rpm_location - link to a download URL of the httpd rpm file

http_version - version string to compare with the currently installed httpd (if any). This needs to match the rpm being downloaded using rpm_location.

rpm_name - variable to allow changing the name of the rpm used temporarily by the role

action - provide capability to reinstall or downgrade using yum. Possible values: reinstall, downgrade, normal

Example Playbook
----------------

```
- name: HTTPD install
  hosts: all
  roles:
    - httpd
```
