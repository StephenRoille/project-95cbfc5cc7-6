Create-React-App
================

Course
------
https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/

Requirements
------------

* virtualbox
* docker toolbox and use host `192.168.99.100` instead of `localhost`)


Section 06
----------
Create a `.env` file containing (see [docs](https://create-react-app.dev/docs/troubleshooting/))

`CHOKIDAR_USEPOLLING=true`

Create the development image

```bash

docker build -f Dockerfile.dev -t stephenroille/app .
```

Map the `node_module` directory and mount the following volume `/proj/project-95cbfc5cc7-6`
into the container (configured in the VirtualBox shared diectories):

```bash

docker run -p 5000:3000 -v /usr/node_app/node_modules -v /proj/project-95cbfc5cc7-6:/usr/node_app -it stephenroille/app
```

