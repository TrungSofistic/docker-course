# Commands

`docker run -p 5173:5173 -v "$(pwd):/app" -v /app/node_modules react-docker`
-> run react-docker image with hot module replacement and node_modules stored in the volume
The -v is to create a docker volume.
`-v "$(pwd):/app"` is to enable HMR
`-v /app/node_modules react-docker` is to store the node modules so docker doesn't have to re-install packages when HMR happens

`docker push trungtrinhh/react-docker`
-> push your docker image publicly so that anyone can pull it (similar to github)
