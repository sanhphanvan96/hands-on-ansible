# Setup environment after install Ubuntu <3

## Vagrant (for testing)

```bash
vagrant init --minimal
```
## Change current directory to ../ex4

```bash
ansible-galaxy --ignore-errors install -p roles -r requirements.yml
ansible-playbook -i hosts.local provision.yml --become
```
## Will be installed:
- git
- docker and docker-compose
- zsh
- oh-my-zsh
- vscode
- apt-fast
- Fcitx-Unikey
