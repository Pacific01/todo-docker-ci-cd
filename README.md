# TodoAPP + Docker + CI/CD

## Build image

```sh
docker build -t todo .
```

## Corre la aplicación

```sh
docker run -p 3000:3000 todo
```

⚠️ Todos juntos vamos a comprobar que si paramos los dockers y los volvemos a
encender la información se pierde ⚠️

Ya podemos parar el contenedor.

## Persistencia de datos

Creamos un volumen:

```sh
docker volume create todo-db
```

Volvemos a ejecutar la app pero con el volumen asociado:

```sh
docker run -p 3000:3000 -v todo-db:/etc/todos todo
```

Como podéis ver esta es una app bastante sencillita, no usa otro contenedor para
la base de datos, simplemente un volumen con la información dentro.
