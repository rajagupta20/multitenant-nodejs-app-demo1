# multitenant-nodejs-app-demo1

This is a single tenant app.

Run below commands to deploy this app to CF

cf create-service xsuaa application multitenant-uaa-1 -c xs-security.json

cf push

