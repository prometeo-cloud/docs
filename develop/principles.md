## Development Principles

- For Ansible good practices refer to the documentation [here]().
- Automation first approach should be used for piece of configuration.
- Each logical automation piece should exist in its own Ansible role.
- Role names should follow the following syntax: PRODUCT_ACTION_TARGET. For example, *jenkins_configure_users*.
- Each Ansible role should exist in its own git role repository
- Each Ansible role should be unit tested with [Molecule]()
- Any playbook which triggers the execution of one or more Ansible roles should exist in its own git configuration repository, with its correspondent *requirements.yml* file pointing to the role repositories required.
- Configuration repositories should be named as follows: CFG_PRODUCT_ACTION_TARGET. For example, *cfg_jenkins_deploy_server*.
- Any playbook which triggers the execution of multiple roles should be integration tested using docker containers and / or vagrant boxes.
- All binaries not deployed via managed yum repositories should be stored in a binary artefact repository such as Nexus or Artifactory.
- Documentation format should be markdown and graphml
- All sensitive information such as IP addresses or secrets should not be pushed to public repositories.
