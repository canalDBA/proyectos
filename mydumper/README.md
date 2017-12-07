## Como compilar MyDumper

Mentor: Maximiliano Bubenik

maxbube tiene un repo que levanta u par de vagrants y _ansibiliza_ este
proceso. El [repo es este](https://github.com/maxbube/mydumper_builder).

En el caso que ya tengas montada la máquina, agregala al ansible_hosts y
hace:

```
ansible-playbook compile_mydumper_debian.yml -i <dir inventorio si tenés varios entornos>
```

Si falla en alguna task, no vuelvas del principio, agregá `--start-at-task="<task name>"`


## Ejemplo

Si bien no es recomendable, podrías cambiar el tx isolation para que sea RC y ganar un 
toque de performance a coste de tener un backup no consistente (pero peude ser útil para
analíticas, ie).

```
- if (mysql_query(thrconn, "SET SESSION TRANSACTION ISOLATION LEVEL REPEATABLE READ")) {
+ if (mysql_query(thrconn, "SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITED")) {
```

Desde el directorio del repo le das a `vagrant up` y listo el pollo.
