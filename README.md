# private-npm-registry
* [blog](https://blog.bitsrc.io/how-to-set-up-a-private-npm-registry-locally-1065e6790796)

## Setup
```
$ mkdir verdaccio && cd verdaccio
$ mkdir conf
$ vi conf/config.yaml

$ mkdir storage
$ mkdir plugins

$ docker run -d \
--publish 4873:4873 \
--volume `pwd`/conf:./verdaccio/conf \
--volume `pwd`/storage:./verdaccio/storage \
--volume `pwd`/plugins:./verdaccio/plugins \
--name verdaccio verdaccio/verdaccio

$ docker ps -a
$ npm adduser --registry http://localhost:4873
Username: rwibawa
Password: ********
Email: (this IS public) ryan.wibawa@gmail.com
Logged in as rwibawa on http://localhost:4873/.

$ mkdir helloworld
$ cd helloworld/
$ vi package.json
$ npm publish --registry http://localhost:4873
```

## UI
[![http://localhost:4873]](docs/verdaccio-ui.jpg)](http://localhost:4873)
