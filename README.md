# CI/CD en Jenkins con nodeJS y un webhook de GitHub para realizar pruebas de building automatizado

* El objetivo es automatizar los Pull Requests o git push de los desarrolladores para que el repositorio tenga configurado un webhook para ejecutar un buid en Jenkins y testar un proyecto de nodeJS.

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
