## salt doc

### returns all grains available on the minion

salt \* grains.ls

### show grain ipv4

salt \* grains.item ipv4


### execute ssh command via minion

salt \* cmd.run 'zfs list'


### show documentation for command

salt \* sys.doc cmd


### debug jinja templates

# returns all available vars / dicts
# add this line to your state file
Context is: {{ show_full_context() }}


# just render a template with args
salt \freebsd_dev slsutil.renderer salt://create_jail/files/rc_conf.jinja default_renderer='jinja' node_name=unbound

# show all available states ( master )
salt '*' state.show_sls '*'

# show all available states ( minion )
salt-call state.show_sls '*'

sudo salt \* slsutil.renderer salt://manage_master/files/master.py


sudo salt \* slsutil.renderer  salt:// state


salt \* state.show_sls <sls_file>
salt \* state.apply <sls_file> test=True


sudo salt \* net.load_template salt://manage_master/files/master.py \
debug=True test=True template_engine=py


### state without a state file
salt \* state.single myjail.online name='unifi'
salt \* state.single pkg.installed name='vim'

### Call a single ID from the named module(s) and handle all requisites
salt '*' state.sls_id id_inside_state state_name pillar='{"foo": "bar"}'
salt '*' state.sls_id create_zfs_filesystem_jails jail.base

### passing arg to state files , mostly for testing

sudo salt 'minion' state.show_sls create_jail saltdev=dev pillar="{'node':'unifi'}"


## debugging fileserver
### show different fileserver envs
### These commands are only available on the master

salt-run fileserver.envs

# Force Update Fileserver
salt-run fileserver.update

# List files on Fileserver
salt-run fileserver.file_list

### exectue command on a minion
### These commands are only available where a minion is installed

# copy something ???
salt-call cp.list_master

### show pillar data for specific minion on master

salt 'example_host' pillar.data

### refresh pillar

salt 'minion1' saltutil.refresh_pillar

### clear minion cache

salt 'minion1' saltutil.clear_cache

### remove the gitfs lock
salt-run cache.clear_git_lock gitfs type=update

