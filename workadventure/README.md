# Things to keep in mind

- download https://raw.githubusercontent.com/workadventure/workadventure/develop/xmpp/ejabberd.template.yml and place that in the xmpp folder that is created, if causes errors like this https://github.com/workadventure/workadventure/issues/3030

Changes already there
- Make sure the file is mounted correctly-       - ~/wa-main/xmpp/ejabberd.template.yml:/opt/ejabberd/conf/ejabberd.template.yml
- Maps are deleted if you do docker compose down apparantely