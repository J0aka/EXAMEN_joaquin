# EXAMEN_joaquin
Crea un repositorio para contestar todo o exame.
Este repositorio ten que conter tódo-los ficheiros necesarios para xustifica-la túas respostas.

Contesta as seguintes preguntas, xustificándoas, nun README.md

1. Explica métodos para 'abrir' unha consola/shell a un contenedor en execución.

En visual-studio si temos instalado e configurado docker poderemos abrir unha consola facendo click dereito nun contenedor do apartadp (containers)

2. No contenedor anterior (en execución), qué opciones tes que ter usado ó arrincalo para poder interactuar coas súas entradas e salidas

Para iso debemos asinarlle de forma manual os portos que tera que empregar.

3. Cómo sería un ficheiro docker-compose para que dous contenedores se comuniquen entre si nunha rede só deles?

Para eso debemos ter unha carpeta co noso proxecto, cun codigo de python nun archivo .py, tamen un .txt cos requirements, e posteriormente crear un dockerfile para lanazar o .py dentro de visual code, finalmente debemos ter un compose.yml como este :

services:  # Define os servizos (contenedores)
  
  <Nome_do_contedor>:
    image: <Imaxe_a_utilizar>
    container_name: <Nome_especifico>
    networks: 
      - <Nome_da_rede>
    command: tail -f /dev/null #Este comando fai que se mantenga activo o contenedor
  <Nome_do_contedor>:
    image: <Imaxe_a_utilizar>
    container_name: <Nome_especifico>
    networks: 
      - <Nome_da_rede>
    command: tail -f /dev/null 
networks:  # Definición das redes
  external: true 

4. Qué tes que engadir ó ficheiro anterior para que un contenedor teña unha IP fixa?

Engadirlle esta liña no apartado networks do .yml
 ipv4_address: Ip que lle queremos asignar a o DNS

5. Qué comando de consola podo usar para sabe-las ips dos contenedores anteriores?


6. Cál é a funcionalidade do apartado "ports" en docker compose?

Serve para o mapeo dos portos host:contenedor

7. Para qué serve o rexistro CNAME? Pon un exemplo

Serve para definir un alias para o nome canónico útil
para suministrar nomes alternativos relacionados con diferentes servicios
no mesmo equipo.

Por exemplo si o resolutor intenta realizar resolución de nomes dun nome que indique o
usuario, non sabe a priori si o nome se refire a un rexistro de recurso (RR) de
direccions de host (A) ou a un CNAME.
Si se refire a un CNAME, o servidor pode
devolver o CNAME.

8. Cómo podo facer para que a configuración dun contenedor DNS non se borre se creo outro contenedor?


9. Engade unha zoa tendaelectronica.int no teu docker DNS que teña:
- www á IP 172.16.0.1
- owncloud sexa un CNAME de www
- un rexistro de texto có contido "1234ASDF"
Comproba que todo funciona có comando "dig"
Mostra nos logs que o servicio funciona ben usando a saída da terminal ó levantar o compose ou có comando "docker logs [nomeContenedorOuID]"
(o apartado 9 realízase na máquina virtual)
