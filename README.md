# latex-thesis-ansible

Playbook for quick installation and first compilation of the
[`thesis`](http://latex.feec.vutbr.cz/sablona/) package
used at [FEEC BUT Brno](http://www.feec.vutbr.cz/fakulta/home.php.en).

This playbook plays well on these systems:
* Fedora
* Debian
* Ubuntu
* Linux Mint

Other distributions are unsupported.

## Requirements

You must have Ansible installed to run this playbook and this repository
must be present on your system.

### Ansible installation
On most distributions there is Ansible available in the distribution repository.
Install it by running
```
# on Debian-based
apt install ansible

# on RedHat-based system
dnf install ansible
```

### Clone the repository
```
git clone https://github.com/ogajduse/latex-thesis-ansible.git
cd latex-thesis-ansible/
```

## Usage
If you are not a root user, you should execute the playbook with the
`--ask-become-pass` option. You will be prompted for sudo password before the
play.

Run the playbook with the default settings.
```
ansible-playbook site.yml --ask-become-pass
```

You can use these variables:
* `download_dir` - location of directory wher the downloaded files will be placed
  * default: */tmp*
* `installation_dir` - location where the directory with `thesis` package will take place
  * default: *~* (your home directory)
* `content_dir` - name of the directory with `thesis` package itself
  * default: *sablona_a_balicek*

Example using extra variables:
```
ansible-playbook site.yml --ask-become-pass \
--extra-vars="download_dir=~/Downloads installation_dir=/tmp content_dir=mythesis"
```
This will download necessary files to your *Downloads* and
it will create directory *mythesis* in the */tmp* directory.

# Issues
In case of issue, don't hesitate to
[open](https://github.com/ogajduse/latex-thesis-ansible/issues/new) one.
