HTTPD
=========

Role to install a specified version of HTTPD onto CentOS 7.x server using an RPM. This includes requesting HAProxy to drain the connections before starting the install and then re-enabling it during clean up.

This role also adds a firewall rule to allow port 80 through firewalld.


Requirements
------------

Ansible 2.6 <

Role Variables
--------------

rpm_location - link to a download URL of the httpd rpm file
http_version - version string to compare with the currently installed httpd (if any)
rpm_name - variable to allow changing the name of the rpm used temporarily by the role

Example Playbook
----------------

- name: HTTPD setup on CentOS
  hosts: all
  roles:
    - httpd
