# kontinuum-deploy

Helper for deployment to [kontinuum](https://github.com/esayemm/kontinuum).

## Install

```
npm i --save-dev kontinuum-deploy
```

## Usage

Obtain kontinuum token by hitting `/get_token` with the correct password.

```sh
DOCKER_EMAIL=<docker email>
DOCKER_PASS=<docker pass>
DOCKER_USER=<docker user>
KONTINUUM_TOKEN=<kontinuum token>

./node_modules/kontinuum-deploy/bin/kontinuum-deploy \
	--input <path to input file> \
	--output <path to outputfile> \
	--service <service name>
```

###Arguments

- input: should be a kubernetes yaml file, what you will be given is IMAGE_NAME so your input should look like the following

```yaml
image: {{IMAGE_NAME}}
```

- output: is where the compiled yaml file will go, preferably right next to the template file so you can manually adjust it if necessary.

- service: will be the name of the service pushed to docker hub `username/<service>:tag`
- dockerFile(optional): location of Dockerfile

## Continious Deployment

Environmental variables should be set in CI.

```json
// package.json
{
	"scripts": {
		"deploy": "./node_modules/kontinuum-deploy/bin/kontinuum-deploy \
			--input <path to input file> \
			--output <path to outputfile> \
			--service <service name>"
	}
}
```

Now you can run `npm run deploy` upon test success.