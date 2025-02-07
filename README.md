<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

## Stack usado

*Nest

*Mongo


# Ejecutar en desarrollo
1. Clonar el repositorio y asignamos al nuevo repo ya creado en git
```bash
git clone https://github.com/martinprado1000/Nest-03-plantilla.git nuevoNombre

git remote set-url origin https://github.com/martinprado1000/nuevoNombre.git
```

2. Tener Nest CLI instalado:
```bash
npm i -g @nest/cli
```

3. Levantar la base de datos. Esta solo dockerizada la base de datos, no la app.
```bash
docker-compose up -d
```

4. Renombrar el archivo __.env.template__ por __.env__ y llenar las variables de entorno e instalar las dependencias:
```bash
#Instalar dependencias
npm install
```

5. Ejecutar en desarrollo
```bash
# Esto ejecuta el archivo docker.compose.yml
$ npm run star:dev

# Ejecutar seed de Pokemons ,inserta multiples datos.
http://localhost:3000/seed/pokemons/multiplesRegistros2
```


# Construir y ejecutar para producción
```bash
# Construir
$ npm run build

# Ejecutar
$ npm run start:prod
```

# Construir y ejecutar para producción la app y la base en mongo DOCKERIZADO

1. Renombrar el archivo __.env.template__ por __.env.prod__ y llenar las variables de entorno.

2. Crear las imagenes
```bash
# Usamos el docker-compose.prod.yaml y el .env.prod que son los de produccón.

docker-compose -f docker-compose.prod.yaml --env-file .env.prod up --build

# Si las imagenes ya fueron creadas y solo necesitamos levantar ejecutar:
docker-compose -f docker-compose.prod.yaml --env-file .env.prod up -d
```

#
### ¿QUE HACE ESTA App?
Configuraciones:

-- Esta aplicacion es la que yo arranque como plantilla, esta contempla:

* Entidades: User, Pokemones, Auth(Hecho por mi SIN jwt ni passport )

* .env  .env.template  .env.prod.

* ConfigModule,ConfigService,Joi.

* Logger Winston. (hecho por mi cuenta)

* CorrelationId. (hecho por mi cuenta)

* Autenticacion y autorizacion. Solo recibe como role: SUPERADMIN, ADMIN, OPERATOR, USER (Solo string en mayuscula, no arreglo) (hecho por mi cuenta).

* Creamos el schema pokemones. (del curso de Herrera).
Busca pokemones all y por id. y creamos semilla de pokemons de 3 formas distintas.

* Si ejecuto en mode dev solo esta dockerizada la db. 

* En prod usamos el archivo docker-compose.prod.yml donde esta dockerizada la app y la db.








