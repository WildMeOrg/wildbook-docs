# Dev Environment Setup

## Prereqs
You need the following installed on your system:
* `default-jdk`
* `build-essential`
* `maven`
* `npm`
* `node`
* `docker-compose`

## System setup
1. Run `sudo sysctl -w vm.max_map_count=262144` (A requirement for OpenSearch, it only needs to be run once on your system.)
1. Run `npm install react-app-rewired`
1. `git clone` your [forked Wildbook repo](pr-workflow.md#fork-wildbook) (referred to as the **code directory** going forward)

### Code directory setup
1. In `devops/development/`, create a `.env` file with a copy the contents of `_env.template`. By default, no changes should be needed.
1. `cd` to the root of the code directory
1. run `npm install`
1. run `chmod +x .husky/pre-commit` to enable husky linting
1. `cd /frontend`
1. run `npm install` to install all dependencies
1. create a `.env` for React environment variables.
    1. Add the public URL: PUBLIC_URL= /react/
    1. Add the site name: SITE_NAME=Amphibian Wildbook

### Deploy directory setup
1. Create your **deploy directory**, matching the value of `WILDBOOK_BASE_DIR` in the .env file. The default is `~/wildbook-dev/`)
1. Create the necessary subdirectories
```
wildbook-dev
|--logs
|--webapps
   |--wildbook
```

### Build war file
To run Wildbook in the development docker environment, even to try out the software, you need a "war file" which is made by compiling the Wildbook java project.

To create the war file:
1. `cd` to the root of the code directory
1. Build your war file with `mvn clean install`
1. verify the war file was created in `target/wildbook-X.Y.Z.war` (where X.Y.Z is the current version number).
1. cd to the deploy directory `cd ~/wildbook-dev/webapps/wildbook` 
1. deploy your warfile `jar -xvf /code/directory/Wildbook/target/wildbook-X.Y.Z.war`

### Deploy
1. `cd` to the `devops/development` directory in the code repo
1. run `docker-compose up [-d]`
1. To verify successful launch, open in browser `http://localhost:81/` when tomcat has started. Default login of username/password `tomcat`/`tomcat123` should work.

Note: if you're running docker as root, you may way to explicitly set your deploy directory path to include your user, i.e., `WILDBOOK_BASE_DIR=~USER/wildbook-dev`

### Redeploy and rebuild
For any local testing, you will need to rebuild and redeploy your changes.

#### War file

If you make code changes and want to test them locally, you can create and deploy a new war file using the [Build war file](#build-war-file) and [Deploy](#deploy) instructions. Then use `docker-compose restart wildbook` to test your changes.

#### React-only changes

If you are working on react-only work, you can test your changes without updating the full war file.
Use npm to build and deploy to your local deployment

If you have your dev environment set up correctly, this will build the React app and copy it into your local deployment directory for you.

1. `cd` to `REPO/frontend/`
1. run `npm run deploy-dev`
1. refresh your browser page by visiting either http://localhost:81/react/ for local testing or https://public.url.example.com/react/ for the public-facing deployment

#### Manually rebuild react-only changes

1. `cd` to `REPO/frontend/`
1. run `npm run build`
1. copy everything under `frontend/build/` to the deployed `wildbook/react/` directory you created during setup
1. refresh your browser page by visiting either http://localhost:81/react/ for local testing or https://public.url.example.com/react/ for the public-facing deployment
