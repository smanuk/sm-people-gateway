# sm-people-gateway

Gateway for routing client calls to services.  Security will be implemented at this edge node.
* it depends on the sm-people-facade

---
###Keycloak setup
Ideally before you start working on the gateway you want to set up your keycloak instance. Keycloak should have been loaded in te Docker container as part of the sm-people-service spin up.

Keycloak is quite a complex product so for the next few steps just focus on what is needed.

Once the keycloak server is running you should be able to browse to the server at http://localhost:40005

Click on the Administration Console link and log in using the crentials specified in the Docker compose file.  In this case user: ***admin*** password: **admin**

Once logged in, create a realm and call in ***demorealm***, no other realm config is required at this.

Now with ***demorealm*** selected click the ***Users*** button in the left menu and click ***Add user*** in the top right of the page.

Add a user named ***demouser*** and click ***save***.

Now click on the ***Credentials*** tab and enter a password for the user in both boxes,  ***Password*** and ***Password Confirmation***.  Then click ***Temporary*** off and click ***Set Password*** button to save the password.  

The gateway should now work against your keycloak installation.

---
###API Documentation

In the postman folder there is a collection that can be imported into Postman.

There 4 API calls in the collection, the **/health endpoint is the only one that does not require authentication and gives the status of the gateway service.

The other 2 @GETS require authentication to progress. Try them without authorisation to see the 401 return code. 

Run the Authorize @POST and copy the "access_token" property value to the ***token*** variable on the collection and save the collection.

Now when you run the 2 @GETS you should get data.
