# Setup environment after install Ubuntu <3

## Vagrant (for testing)

```bash
vagrant init --minimal
```
## Change current directory to ../ex4

```bash
ansible-galaxy --ignore-errors install -p roles -r requirements.yml # no need
ansible-playbook -i hosts.local -l ci provision.yml --become -u$(whoami) # change group `ci`
```
## Will be installed:
- git
- docker and docker-compose => Deploy application: [https://github.com/sanhphanvan96/WebsiteChoThuePhongTro](https://github.com/sanhphanvan96/WebsiteChoThuePhongTro)
- zsh
- oh-my-zsh
- vscode
- apt-fast
- fcitx-Unikey
