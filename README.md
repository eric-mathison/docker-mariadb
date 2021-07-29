# MariaDB Docker Image

This image is based off the official [MariaDB](https://hub.docker.com/_/mariadb) Docker image with a slight adjustment, the image doesn't run as `root`. This image runs as a non-root user `mysql`.

## Using this Image

### Start a `mariadb` server instance

```bash
$ docker run -p 127.0.0.1:3306:3306  --name some-mariadb -e MARIADB_ROOT_PASSWORD=my-secret-pw -d eric-mathison/mariadb:10
```

## Configuration

### Environment Variables

```
    MYSQL_ROOT_PASSWORD: root_password
    MYSQL_DATABASE: database_to_be_created
    MYSQL_USER: username_to_be_created
    MYSQL_PASSWORD: password_for_user_created
```

### GH Actions

This repo is configured to automatically build this Docker image and upload it to your Docker Hub account.

1. To setup this action, you need to set the following enviroment secrets:

-   `DOCKERHUB_USERNAME` - this is your Docker Hub username
-   `DOCKERHUB_TOKEN` - this is your Docker Hub API key

2. You need to update the tags for the build in `/.github/workflows/deploy.yml` on line 26.
