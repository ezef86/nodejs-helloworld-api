# CI/CD en Jenkins con nodeJS y un webhook de GitHub para realizar pruebas de building automatizado

* El objetivo es automatizar los Pull Requests o git push de los desarrolladores para que el repositorio tenga configurado un webhook para ejecutar un buid en Jenkins y testar un proyecto de nodeJS.

## Configuración en Jenkins:

* Corroborar que esté instalado o instalar el plugin "GitHub Branch Source".
* Crear un nuevo item, darle un nombre y elegir "Multibranch Pipeline".
* En la configuración del nuevo job, dentro de "Branch Sources" agregar la URL del repositorio de GitHub con el que Jenkins se comunicará. Si tiene credenciales, agregarlas también.
* En la sección "Build Configuration" asegurarse que la ruta del Jenkinsfile coincida con la ubicación en el repositorio de GitHub.
* Aplicar y guardar.

### Configuraciones adicionales:

Al ejecutar una aplicación de nodeJS se debe instalar el plugin "NodeJS" para luego ir a System Configuration >> Tools >> NodeJS Installations >> Add NodeJS:
* El nombre de la nueva instalación debe coincidir con el nombre ingresado en el Jenkinsfile en el bloque tools {}
* En este caso sería "nodejs21"
* Elegir la versión de nodeJS que se requiera para el entorno, en este caso se elige "NodeJS 21.7.3"
* Aplicar y guardar.
  
## Ejecutar en entorno local:

### Clonar el repositorio:
```bash
git clone https://github.com/edgaregonzalez/nodejs-helloworld-api.git
cd nodejs-helloworld-api
```

### Instalar dependencias:
```bash
npm install
```

### Ejecutar las pruebas:
```bash
npm test
```

### Correr el servidor:
```bash
npm start
```

### Realizar un requerimientopara que devuelva el mensaje:
```bash
curl http://localhost:3000
```
