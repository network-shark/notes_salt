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
salt '*' state.sls_id my_state my_module pillar='{"foo": "bar"}'

### passing arg to state files , mostly for testing

sudo salt 'minion' state.show_sls create_jail saltdev=dev pillar="{'node':'unifi'}"


## debugging fileserver
### show different fileserver envs

salt-run fileserver.envs


### exectue command on a minion
salt-call

salt-call cp.list_master


