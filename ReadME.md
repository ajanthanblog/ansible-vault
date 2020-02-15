This is an article on a common use case, we face during ansible automation - where in our group_vars and host_vars we used to define the common passwords and also in the hosts file we will have our ssh passwords which needs to be encrypted, as it have the sensitive data. Ansible Vault provides us with a solution for this kind of use case.

In this article I'm going to provide a step by step guide on how we can use the Ansible Vault to achieve our requirement as mentioned above. Here my main intention is to
1) Encrypt specific variables in group_vars files
2) Encrypt specific variables in host_vars files
3) Encrypt the whole file hosts 
4) How to Edit the Encrypted variables

To start on this first i'll create the recommended best practice directory structure for the Ansible Scripting, for that execute the below:
For more information can refer:
[1] https://medium.com/swlh/automating-the-server-management-with-ansible-8fa464379fa9

mkdir -p inventories/{production,staging}/{group_vars,host_vars}
touch inventories/{production,staging}/hosts
mkdir -p library module_utils filter_plugins
mkdir -p roles/common/{tasks,handlers,templates,files,vars,defaults,meta,library,module_utils,lookup_plugins}
touch site.yml roles/common/{tasks,handlers,templates,files,vars,defaults,meta}/main.yml

