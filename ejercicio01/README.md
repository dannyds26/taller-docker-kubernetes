
# Ejercicio 1

Contentedor nginx


## Authors

- [@dannyds26](https://www.github.com/dannyds26)


## Run Locally

Clone the project

```bash
  git clone https://github.com/dannyds26/taller-docker-kubernetes.git
```

Go to the project directory

```bash
  cd ejercicio01
```

Start the server

```bash
  docker run --rm --name ejercicio01-nginx -v $(pwd):/usr/share/nginx/html:ro -d -p 8080:80 nginx
```

Visit web page

```bash
  http://localhost:8080/
```
