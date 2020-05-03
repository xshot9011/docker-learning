# make it producetion grade

(start) >> development >> testing >> deployment >> (start)

using DOckerfile.dev

ิbut docker cannot find Dockerfile.dev

you need to run another command to build image

```bash
docker build -f Dockerfile.dev .
```
## making this app

note: install node is required

```bash
npm install -g create-react-app
cd [to the directody]
create-react-app [name]
```

## nodejs command

### startup deveopment server

```bash
npm run start
```

### run test associated with project

```bash
npm run test
```

### build a production version of application

```bash
npm run build
```