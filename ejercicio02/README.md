
# Ejercicio 2

A brief description of what this project does and who it's for


## Authors

- [@dannyds26](https://www.github.com/dannyds26)


## Run Locally

Pull docker image

```bash
  docker pull nicopaez/pingapp:3.0.0
```

Tag the image

```bash
  docker tag nicopaez/pingapp:3.0.0 dannyds26/pingapp:3.0.0
```

Login to dockerhub
```
  docker login --username dannyds26
```

Push the new image

```bash
  docker push dannyds26/pingapp:3.0.0
```

Pull the new image

```bash
  docker pull dannyds26/pingapp:3.0.0
```
