Ansible Role: bootstrap
================================================================================

Install some packages and deploy some files on RHEL/CentOS, FreeBSD, or Ubuntu.

- Install packages for development: autoconf, automake, git, patch, and so on.
- Install utilitiy packages: zip, bzip2, bash, zsh, wget, ...
- Install Python related packages
- Deploy /root/.proffile, /root/.exrc, /etc/motd

Requirements
--------------------------------------------------------------------------------
No requiremetns.

Role Variables
--------------------------------------------------------------------------------
These variables are defined in `defaults/main.yml` file for being removed and
installed packages on each supported platform.

```yaml
packages:
  freebsd:
    removed: []
    install:
      devel: [
        'autoconf', 'automake', 'gcc', 'gettext', 'git', 'ncurses', 'openssl',
        'patch', 'pcre', 'readline'
      ]
      utils: ['bzip2', 'zip', 'bash', 'wget', 'ja-nkf', 'bash', 'zsh']
      python: ['python27', 'py27-pip', 'py27-virtualenv']
  redhat:
    removed: []
    install:
      devel: [
        'autoconf', 'automake', 'gcc', 'gcc-c++', 'gettext', 'gettext-devel',
        'git', 'ncurses', 'ncurses-devel', 'openssl-devel', 'patch', 'pcre',
        'pcre-devel', 'perl-core', 'readline', 'readline-devel'
      ]
      utils: ['bzip2', 'zip', 'zlib', 'zlib-devel', 'bc', 'wget', 'telnet', 'finger']
      python: ['python-setuptools', 'libselinux-python']
  debian:
    removed: []
    install:
      devel: [
        'autotools-dev', 'autoconf2.59', 'automake1.11', 'gcc', 'gettext', 'git',
        'libncurses-dev', 'libpcre3', 'libpcre3-dev', 'libreadline6-dev',
        'libreadline6', 'ncurses-dev', 'openssl', 'patch'
      ]
      utils: ['bzip2', 'zip', 'zlib1g', 'zlib1g-dev', 'bc', 'wget', 'telnet', 'finger']
      python: ['python-pip', 'python-selinux', 'python-virtualenv']
```

Dependencies
--------------------------------------------------------------------------------
None

Example Playbook
--------------------------------------------------------------------------------
```yaml
- hosts: servers
  roles:
     - azumakuniyuki.bootstrap
```

License
--------------------------------------------------------------------------------
BSD

Author Information
--------------------------------------------------------------------------------
[azumakuniyuki](http://nyaan.jp/)
