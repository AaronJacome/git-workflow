## ¿Qué es git?

* `Sistema de control de versión distribuido`

- Creado por Linus Torvalds

- Ligero (uso snapshots)

- Crear `branch`

![alt text](https://git-scm.com/book/en/v2/images/distributed.png "Diagrama control de versión distribuido")

## Ciclo de vida Git

1.Iniciar repositoro

* `Clonar` repositorio si ya existe

```git
git clone #urlAClonar
```

* o Iniciar repositorio local

```git
git init
```

2. Modificar y/o crear archivos

3. Agregar Archivos editados al area `staging`

* Agregar todos los archivos
  ```git
  git add .
  ```
* Agregar un archivo especifico
  ```git
  git add config.js
  ```

4. Hacer commit de archivos en `stagin`

```git
  git commit -m "Mensaje descriptivo de los cambios realizados"
```

5. Hacer `push` de los cambios al servidor de ser necesario

```git
git push origin master
```

![alt text](https://git-scm.com/figures/18333fig0201-tn.png "flujo básico git")

## Flujo de trabajo

1. Todo lo que existe dentro del `repositorio master` debe estar listo para producción

2. Hacer `fork` al `repositorio master`

3. Para trabajar en algo nuevo es necesario crear un `branch` de `master` con un nombre descriptivo

4. Hacer `commits` locales y regulares en el branch, hacer `push` a una branch

5. Cuando este listo para hacer `merge` al `repositorio principal` o se require ayuda o feedback se debe abrir un `pull request`

6. Despues de que los cambios sean revisados y aprovados en el `pull request` se hace `merge` al `repositorio master`

7. Al hacer merge se debe de enviar a producción lo antes posible

8. Hacer `pull` a los cambios en master y reiniciar el ciclo ( volver a 3)

## Merge vs Rebase

Los dos son herramientas para integrar cambios entre diferetentes branchs, la principal diferenca radica en que merge crea un commit nuevo que relaciona las dos branchs y rebase toma todos los commits de un branch y los reescribe en el historial de la nueva

**Advertencia**

Evitar el uso de rebase en un repositorio compartido ya que reescribe la historia

## Comandos básicos

* `git init`: Inicializa git en un repositorio local
* `git clone @urlRepositorio`: crea una copia local de un repositorio
* `git add @file`: Agrega los archivos modificados al área de stagin
* `git branch`: Lista todas las branch locales e indica en que branch nos encontramos
* `git branch @branch`: Crea un branch nuevo con el nombre utilizado
* `git checkout @branch`: Cambia el branch activa a la indicada
* `git checkout @commitHash`: Regresa al estado que se encontraba en un commit particular
* `git checkout -b #nombreDelBranch`: Crea un branch con el nombre inidicado y asigna el branch nuevo como la activa. (implica: `git branch @branch` + `git checkout @branch` )
* `git remote`: lista todos los nombres de los`remotes` asignados al repositorio local
* `git remote -v`: lista todos los `remotes` con su url
* `git remote add @nombre @url`: agrega un nuevo remote con su nombre y la url para obtener cambios
* `git fetch @nombreRemote`: Obtiene commits y branch de un remote
* `git merge @branch`: crea un nuevo commit e une los cambios de la branch seleccionada a la branch actual
* `git pull @remoteName @remoteBranch`: obtiene los commits del branch remoto y los fusiona con el branch actual
* `git push @remoteName @remoteBranch`: sube los commits locales y los combina en el branch remoto
* `git config [options]`: muestra la configuracion de git local o remota
* `git reset @file`: regresa el estado del archivo al ultimo commit
* `git reset --hard head`: quita todos los cambios del area de staging y regresa el branch a su ultimo commit
* `git status`: Muestra los archivos que estan en stagin o archivos nuevos y la diferencia de commits entre el branch local y el remote

## Glosario

* **Sistema de control de versión distribuido:** todos los equipos cuentan con una copia completa incluyendo el historial.

* **Branch:** git crea un nuevo puntero dirigido a un punto en especifico en el historial y permite crear una nueva historia a partir del mismo sin dañar, modificar o eliminar la linea original

* **Clonar:** Obtener una copia idéntica e independiente de un repositorio remoto en el equipo local

* **Stagin:** estado en el que se encuentra un archivo despues de ser editado pero antes de hacer el cambio permanente (`commit`)

* **Push:** Enviar todos los `commits`locales al repositorio remoto

* **Pull:** Obtener todos los commits remotos y hacer `merge` al branch actual

* **Repositorio Master:** Repositorio principal, siempre listo para lanzar a producción y no puede ser editado directamente

* **Fork:** Obtener una copia idéntica e independiente de un repositorio almacenado de manera remota, pero mantiene una referencia al repositorio principal

* **Commit:** Guardar los cambios realizados al doucmento el la BD de git local

* **Merge:** Forma de integrar cambios entre dos branch fusionando dos ramas

* **Rebase:** Forma de integrar cambios entre dos ramas, reorganizando los commits de una de ellas

* **Pull Request:** Es una petición que realiza el propietario de un `fork`al propietario del repositorio original para incorporar los commits que están en una rama particular del fork al repositorio principal

* **Upstreams:** Repositorios remotos de los cuales podemos obtener cambios

* **Fetch:** Accion de obtener los commits remotos de un upstream sin integrarlos a ningun branch

* **HEAD:** último commit del branch

## Referencias

* [Sitio oficial git](https://git-scm.com/docs)
* [github workflow](https://guides.github.com/introduction/flow/)

**Imagenes proporcionadas por [git-scm](https://git-scm.com)**
