# multitenant-nodejs-app-demo1

This is a basic multi-tenant app.


Run below commands to deploy this app to CF

cf create-service xsuaa application multitenant-uaa-1 -c xs-security.json

cf create-service saas-registry application saas-registry-1 -c config.json

cf push

-------
The app does not create route on subscription. You need to manually create the route.

cf map-route APP_NAME DOMAIN [--hostname HOSTNAME] [--path PATH]

If consumer Account subdomain is: "consumer1". Run below command

cf map-route approuter-multitenant cfapps.eu10.hana.ondemand.com --hostname consumer1-approuter-multitenant-12345-1.cfapps.eu10.hana.ondemand.com


FInal URL for consumer 1 will be:
https://consumer1-3xr9bx8n-approuter-multitenant-12345-1.cfapps.eu10.hana.ondemand.com/

You may also create route in BTP cockpit.


