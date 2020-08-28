=== Overview

New monolithic Ansible playbook, `main.yml` and supporting files  which is designed for teaching and training in refacoring and
the use of roles, collections etc.
Designed to replace the function of the old link:https://github.com/tonykay/bad-ansible[`bad-ansible`] with a different
approach, i.e. start with a fully functional playbook and teardown and iteratively refactor.


==== Quick Start

Assumes a configuration matching an AgnosticD `three-tier-app` with a `devops` service account.

. Deploy

+
[source,bash]
----
ansible-playbook main.yml
----


=== Overall Architecture 

image::.images/ntier-app-topology.png[role="thumb center" width=80%]

*Concept change from `bad-ansible`*

n-tier app is designed to be well written *but* monolithic in its construction
to all useful exercises in refactoring, introducing modularity, and a backdrop
to create roles and or collections from sound a sound ansible code base.

=== Outline of main flow

* common
** setup yum repos (via satellite)
** setup firewalld
* setup postgres
** firewalld rule opening 5432
** install postgres 10
** no data load phase - come back to that?
* setup app tier
** firewalld rule opening 443

=== Development Environment

While intended to be deployed on a _real_ cloud or virtualization platform it
comes with a Vagrantfile and associated playbooks

==== Deploying the Database Tier


=== Notes:

Does firewalld need to be configured?

=== Resources

* Jeff Geerling's Ansible Galaxy Role
* Useful articles on Postgres
** Setting it up from scratch

https://opensource.com/article/17/6/ansible-postgresql-operations
  


== Credits

* Aditya Patawari and Vikas Aggarwal
** I used their phone app during debugging
** Shout out for their Ansible Automation Cookbook
* Jeff Geerlinguy for his Ansible Galaxy Postgres Role

