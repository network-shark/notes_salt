

create
copy pillar from other jail
pillar/{jailname}.sls

change jail_name , jail_hostname , jail_minion_name
change jail_ip , jail_interface

copy template from other jail
create state/jail/{jailname}

change map.jinja
change init.sls


add your jail to pillar/top.sls

add your new jail under the hypervisor

# optional  , just for highstate
add the jail inside states

