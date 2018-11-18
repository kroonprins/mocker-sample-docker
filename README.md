See [this sample application](https://github.com/kroonprins/mocker-sample) first for more information.

Set the environment variables as described in [here](https://github.com/kroonprins/mocker-sample) in a .env file

To run the UI:
```shell
docker run --rm \
  -p 3000:3000 -p 3001:3001 -p 3002:3002 -p 3003:3003 -p 3004:3004 -p 3005:3005 \
  -v $(pwd)/projects:/app/projects \
  -v $(pwd)/rules:/app/rules \
  -v $(pwd)/.env:/app/.env \
  -v $(pwd)/template-helpers.nunjucks.mjs:/app/template-helpers.nunjucks.mjs \
  kroonprins/mocker:latest \
  npm start
```

To start the mock server for a project from the command line instead of the UI:
```shell
docker run --rm \
  -p 3000:3000 \
  -v $(pwd)/projects:/app/projects \
  -v $(pwd)/rules:/app/rules \
  -v $(pwd)/.env:/app/.env \
  -v $(pwd)/template-helpers.nunjucks.mjs:/app/template-helpers.nunjucks.mjs \
  kroonprins/mocker:latest
```

To start the mock server with swagger UI enabled for a project from the command line instead of the UI:
```shell
docker run --rm \
  -p 3000:3000 -p 3006:3006\
  -v $(pwd)/projects:/app/projects \
  -v $(pwd)/rules:/app/rules \
  -v $(pwd)/.env:/app/.env \
  -v $(pwd)/template-helpers.nunjucks.mjs:/app/template-helpers.nunjucks.mjs \
  kroonprins/mocker:latest
```
(the swagger UI is enable by setting MOCKER_MOCK_SERVER_SWAGGER_UI_ENABLED=true in .env)

To start the  learning mode reverse proxy server for a project from the command line instead of the UI:
```shell
docker run --rm \
  -p 3002:3002 \
  -v $(pwd)/projects:/app/projects \
  -v $(pwd)/rules:/app/rules \
  -v $(pwd)/.env:/app/.env \
  -v $(pwd)/template-helpers.nunjucks.mjs:/app/template-helpers.nunjucks.mjs \
  kroonprins/mocker:latest \
  npm run learning-mode
```
