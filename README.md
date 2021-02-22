The lab script deploys a global Ansible configuration file to /etc/ansible/
ansible.cfg. This global Ansible configuration file sets become: true. The
become: true setting makes playbooks execute as the root user. The lab
script runs as the root user and logs in to OpenShift as a user with administrator
privileges.
The k8s.yml playbook specifies become: false to override the global
configuration. This is required so the playbook executes as the student user,
whose kubeconfig file is configured to interact with OpenShift as the developer
user. Otherwise, the playbook tasks would execute as the root user and interact
with OpenShift as a user with administrator privileges.
