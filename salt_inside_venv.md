### create a virtual env , in this case salt3004
`python3 -m venv .venv/salt3004`
### enable venv
`source .venv/salt3004`

### install salt
`pip instal salt`
```
`ln -s /root/.venv/salt3004/bin/salt salt`
`ln -s /root/.venv/salt3004/bin/salt-call salt-call`
`ln -s /root/.venv/salt3004/bin/salt-cp salt-cp`
`ln -s /root/.venv/salt3004/bin/salt-key salt-key`
`ln -s /root/.venv/salt3004/bin/salt-master salt-master`
`ln -s /root/.venv/salt3004/bin/salt-minion salt-minion`
`ln -s /root/.venv/salt3004/bin/salt-proxy salt-proxy`
`ln -s /root/.venv/salt3004/bin/salt-run salt-run`
`ln -s /root/.venv/salt3004/bin/salt-unity salt-unity`
```

### you have to steal the init.d scripts from somewhere


