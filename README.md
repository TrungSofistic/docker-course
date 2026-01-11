# Resources:

- [The video](https://www.youtube.com/watch?v=GFgJkfScVNU)
- [Video resources](https://jsmastery.com/video-kit/e27c9ec5-c768-4ebd-85de-f8836f6c07de)
- [Notion node](https://www.notion.so/trungtrinhh/Docker-Tutorial-2e5fc6d4e44880f1817af7ed0b2b4fd7?source=copy_link)
- [Docker cheat sheet](https://github.com/TrungSofistic/docker-course/blob/main/Docker%20Cheat%20Sheet.pdf)

# Commands

- Create a docker image:
  `docker build -t react-docker .`
  -> creating a docker image called react-docker from the current directory using the `Dockerfile` instructions
  -> try in react-docker folder

- Run an image, aka container creation
  `docker run -p 5173:5173 -v "$(pwd):/app" -v /app/node_modules react-docker`
  -> run react-docker image with hot module replacement and node_modules stored in the volume
  The -v is to create a docker volume.
  `-v "$(pwd):/app"` is to enable HMR
  `-v /app/node_modules react-docker` is to store the node modules so docker doesn't have to re-install packages when HMR happens
  -> try in react-docker folder

- Publish your image to docker hub:
  `docker push trungtrinhh/react-docker`
  -> push your docker image publicly so that anyone can pull it (similar to github)
  -> try in react-docker folder

- Setup docker files in a repository:
  `docker init`
  -> used this in vite-project folder

- Running docker configurations
  `docker compose up`
  -> this command will run the docker image with configurations in `compose.yaml`
  -> used this in vite-project folder

- `docker compose watch`
  Similar to `docker compose up` but with HMR
  -> used this in vite-project or mern-docker folder

# Notes

- Node that `Dockerfile` is needed per container -> see in `mern-docker`
- `compose.yaml` is needed when you want to run both systems in 1 command -> see in `mern-docker`
- In mern-docker:
  - we're showing how to have the frontend, backend and database running with just `docker compose watch`
  - See compose.yml in the root folder to see how these were configured
- Project example sequence: hello-docker -> vite-project -> mern-docker -> next-docker
- Run `docker compose up` for production and `docker compose watch` for development
  - `docker compose up` - Starts containers without file watching
  - `docker compose watch` - Starts containers WITH file watching and HMR
