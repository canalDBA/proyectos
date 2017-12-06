## Como compilar MyDumper

maxbube tiene un repo que levanta u par de vagrants y ansiliza este
proceso. El [repo es este](https://github.com/maxbube/mydumper_builder).

En el caso que ya tengas montada la máquina, agregala al ansible_hosts y
hace:

```
ansible-playbook compile_mydumper_debian.yml -i <dir inventorio si tenés varios entornos>
```

Si falla en alguna task, no vuelvas del principio, agregá `--start-at-task="<task name>"`
