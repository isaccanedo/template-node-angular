<p align="center">
    <a href="http://kitura.io/">
        <img src="https://landscape.cncf.io/logos/ibm-member.svg" height="100" alt="IBM Cloud">
    </a>
</p>

<p align="center">
    <a href="https://cloud.ibm.com">
    <img src="https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg" alt="IBM Cloud">
    </a>
    <img src="https://img.shields.io/badge/platform-node-lightgrey.svg?style=flat" alt="platform">
    <img src="https://img.shields.io/badge/license-Apache2-blue.svg?style=flat" alt="Apache 2">
</p>

# Angular UI Patterns with Node.js

Angular é uma estrutura popular para criar interfaces de usuário em componentes modulares. Neste aplicativo de amostra, você criará um aplicativo da web usando Express e Angular para servir páginas da web em Node.js, completo com as melhores práticas padrão, incluindo uma verificação de integridade.

This application contains 12 popular UI patterns that make it very easy to construct a dashboard application.

This app contains an opinionated set of components for modern web development, including:

* [Angular](https://angular.io/)
* [Webpack](https://webpack.github.io/)
* [Sass](http://sass-lang.com/) 
* [gulp](http://gulpjs.com/)
* [Carbon](https://www.carbondesignsystem.com/)

## Steps

You can deploy this application to IBM Cloud or build it locally by cloning this repo first. Once your app is live, you can access the `/health` endpoint to build out your cloud native application.

### Deploying 

Make sure you are logged into the IBM Cloud using the IBM Cloud CLI and have access 
to you development cluster. If you are using OpenShift make sure you have logged into OpenShift CLI on the command line.

```$bash
npm i -g @ibmgaragecloud/cloud-native-toolkit-cli
```

Use the IBM Garage for Cloud CLI to register the GIT Repo with Jenkins 
```$bash
igc pipeline
```

### Building Locally

To get started building this application locally, you can either run the application natively or use the [IBM Cloud Developer Tools](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started) for containerization and easy deployment to IBM Cloud.

#### Native Application Development

Install the latest [Node.js](https://nodejs.org/en/download/) 6+ LTS version.

Once the Node toolchain has been installed, you can download the project dependencies with:

```bash
npm install
cd client; npm install; cd ..
npm run build
npm run start
```

Modern web applications require a compilation step to prepare your ES2015 JavaScript or Sass stylesheets into compressed Javascript ready for a browser. Webpack is used for bundling your JavaScript sources and styles into a `bundle.js` file that your `index.html` file can import. 

***Webpack***

For development mode, use `webpack -d` to leave the sources uncompress and with the symbols intact.

For production mode, use `webpack -p` to compress and obfuscate your sources for development usage.

***Gulp***

Gulp is a task runner for JavaScript. You can run the above Webpack commands in by running:
```bash
gulp
```

To run your application locally:
```bash
npm run start
```

Your application will be running at `http://localhost:3000`.  You can access the `/health` and `/appmetrics-dash` endpoints at the host.

<!--
#### IBM Cloud Developer Tools

Install [IBM Cloud Developer Tools](https://cloud.ibm.com/docs/cli?topic=cloud-cli-getting-started) on your machine by running the following command:
```
curl -sL https://ibm.biz/idt-installer | bash
```

Your application will be compiled with Docker containers. To compile and run your app, run:
```bash
ibmcloud dev build
ibmcloud dev run
```

This will launch your application locally. When you are ready to deploy to IBM Cloud on Cloud Foundry or Kubernetes, run one of the following commands:
```bash
ibmcloud dev deploy -t buildpack
ibmcloud dev deploy -t container
```

You can build and debug your app locally with:
```bash
ibmcloud dev build --debug
ibmcloud dev debug
```
-->

##### Session Store

You may see this warning when running `ibmcloud dev run`:
```
Warning: connect.session() MemoryStore is not
designed for a production environment, as it will leak
memory, and will not scale past a single process.
```

When deploying to production, it is best practice to configure sessions to be stored in an external persistence service.

## Next Steps

* Learn more about augmenting your Node.js applications on IBM Cloud with the [Node Programming Guide](https://cloud.ibm.com/docs/node?topic=nodejs-getting-started).
* Explore other [sample applications](https://cloud.ibm.com/developer/appservice/starter-kits) on IBM Cloud.

## License

This sample application is licensed under the Apache License, Version 2. Separate third-party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1](https://developercertificate.org/) and the [Apache License, Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache License FAQ](https://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)




