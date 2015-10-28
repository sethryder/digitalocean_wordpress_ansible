## WordPress Deployment (for Digital Ocean CentOS 7.1)

This is a modified playbook of the Ansible example playbook modified to
work on CentOS 7.1 on Digital Ocean.

- Requires Ansible 1.2 or newer
- Expects CentOS/RHEL 7.x host/s

These playbooks deploy a simple all-in-one configuration of the popular
WordPress blogging platform and CMS, frontend by the Nginx web server and the
PHP-FPM process manager. To use, copy the `hosts.example` file to `hosts` and 
edit the `hosts` inventory file to include the names or URLs of the servers
you want to deploy.

Then run the playbook, like this:

	ansible-playbook -i hosts site.yml

The playbooks will configure MariaDB, WordPress, Nginx, and PHP-FPM. When the run
is complete, you can hit access server to begin the WordPress configuration.

### Recommended Changes

If you plan on using this in a production enviorment, it is HIGHLY recommended
that you change the default wordpress database name, username, and password in
the `group_vars/all` file.

### Ideas for Improvement

Here are some ideas for ways that these playbooks could be extended:

- Parameterize the WordPress deployment to handle multi-site configurations.
- Separate the components (PHP-FPM, MySQL, Nginx) onto separate hosts and 
handle the configuration appropriately.
- Handle WordPress upgrades automatically.
