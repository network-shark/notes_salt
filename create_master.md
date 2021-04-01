# create rootless salt
mkdir -p etc/salt srv/salt/pillar srv/salt/states var/log/salt

touch  etc/salt/master etc/salt/roster

# master example
user: sharky

root_dir: /Users/sharky/python/salt/salt-sproxy_work/
config_file: /Users/sharky/python/salt/salt-sproxy_work/etc/salt/master
roster_file: /Users/sharky/python/salt/salt-sproxy_work/etc/salt/roster
pillar_roots:
  base:
    - /Users/sharky/python/salt/salt-sproxy_work/srv/salt/pillar

file_roots:
  base:
    - /Users/sharky/python/salt/salt-sproxy_work/srv/salt/states/base


# roster example
freebsd:
  host: <host>
  username: <user>
  password:  <password>




