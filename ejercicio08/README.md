
# Ejercicio 8

Creación de cluster balanceado

## Authors

- [@dannyds26](https://www.github.com/dannyds26)

## Run Locally

Start services

```bash
  docker compose up --scale app=2
```

Open application

```bash
  http://localhost:8080/
```

## Health check

Al ejecutar varias veces el url http://localhost:8080/health, se obtienen respuestas como las siguientes:

```
{"host":"d2ce92639831","loadavg":[1.19873046875,1.46728515625,1.55126953125],"freemem":1559322624,"appversion":"1.0.0"}
{"host":"b451b53c7bd5","loadavg":[1.00537109375,1.404296875,1.5283203125],"freemem":1556553728,"appversion":"1.0.0"}
{"host":"d2ce92639831","loadavg":[0.9248046875,1.380859375,1.52001953125],"freemem":1545117696,"appversion":"1.0.0"}
{"host":"b451b53c7bd5","loadavg":[0.93701171875,1.3681640625,1.51416015625],"freemem":1560932352,"appversion":"1.0.0"}
```

En el campo `host` se puede ver quién sirve la petición. En este caso, varia debido a que el balanceador está haciendo el trabajo de distribuir la carga a alguna de las instancias que estan corriendo.

El ejecutar el docker compose con la confiuguración `--scale app=2` le estamos indicando al docker que cree 2 contenedores con la imágen `nicopaez/password-api`.