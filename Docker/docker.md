Docker is an containerization platform, which builds images of applications along with any base image (OS) and other dependencies. Then, in dorder to combine them into a container to be deployed, it bundles all the image files in a single isolated container. The Containers are toatally isolated from the outside environment. all the processes will be running in the container without spilling over its processes outside

We can run containers from the public images created and uploadedo the [Docker-Hub](https://hub.docker.com) Or we can create images of our custom App using [Dockerfile](https://docs.docker.com/engine/reference/builder/) and run it in a Container. Dockerfile is is made of simple `YAML` file format, which is not intimaidating to newcomers, but we need to keep the **Indenting in mind**. A sample of Dockerfile is:

```
cat Dockerfile

FROM nginx:latest

COPY index.html /usr/share/nginx/html
COPY linux.png /usr/share/nginx/html

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
```

In above file we've used a `yaml` file describing our requirements:

- [FROM](https://docs.docker.com/engine/reference/builder/#from) specifies the **base image to use** as the starting point for this new image you're creating. For this example we're starting from `nginx:latest`.
- [COPY](https://docs.docker.com/engine/reference/builder/#copy) copies files from the host into the image, at a known location. In our case it copies `index.html` and a graphic that will be used on our webpage.
- [EXPOSE](https://docs.docker.com/engine/reference/builder/#expose) documents which ports the application uses.
- [CMD](https://docs.docker.com/engine/reference/builder/#cmd) specifies what command to run when a container is started from the image. Notice that we can specify the command, as well as run-time arguments.
