# Electron runner for development

This image provides development environment for the Electron
applications.

To run your application run in folder containing your application:

```bash
$ docker run --rm -it -v $(pwd):/app --network host -e DISPLAY=$DISPLAY -e "${HOME}/.Xauthority:/root/.Xauthority:rw" docker.pkg.github.com/struchu/electron-runner/runner:0.1.0 npm run start:dev
```

> Note: please tweak the command that starts your app.

Alternatively you can add service to your `docker-compose.yml` file:

```yml
services:
    electron:
        image: docker.pkg.github.com/struchu/electron-runner/runner:0.1.0
        network_mode: "host"
        environment:
            DISPLAY: "${DISPLAY}"
        volumes:
            - .:/app
            - "${HOME}/.Xauthority:/root/.Xauthority:rw"
        command: ["npm", "run", "start:dev"]
```

