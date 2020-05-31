## Kobil Cloud Connector  v1.4.0.beta.158 

<br/>

### **Docker Download**


### kobil/kobil-cloud-connector:1.4.0-beta.158
**DIGEST:** sha256:aefa997182280123682c56dbe57cf8b3d5792c44ef26e2b94987eca19a75aa23

<br/>

### kobil/kobil-cloud-pooler:1.4.0-beta.43
**DIGEST:** sha256:11e7721c423750e8dc0dd914e331bad9165b4ed89b5fdac15a1f1ae3226a4aaa

------------------------------------

We're constantly working to improve your KOBIL Cloud Connector experience, here's a summary of what has changed

<br/>

### What's new
* GetTransactionResult: Added new feature which would be helpful for users in retrieving the transaction result using unique transaction ID over a period of 24 hours. This is configurable with pooler.transaction.persistenttimeout in seconds under connector.properties file.
* Event Controller: Monitoring the SSMS events made easier now with this new module which helps the users in retrieving the details of dead events, subscribe/unsubscribe the events.

<br/>

### Improvements
* Increased API efficiency in handling the failure events with DeadEvents API for the major functionalities (CreateTransaction, VerifyOnlineQr). 
* Users have provision to subscribe to their required events. Another interesting event is to stream the live events and display it to the user.
* Refined message content in the response for better readability (which does not impact the overall functionality) in these API’s - DeleteAppUpdate, EditAppVersion, AssignVersionUpdate, EditApp, CreateApp.
* Added "ttl" optional parameter in CreateActivationCode API, this  API have an “activationNotAfter” option, which is hard to calculate the timestamp, so adding ttl in timeunit as an option in request body to calculate the “activationNotAfter”. (If “activationNotAfter” is present, then “ttl” should not be taken into account)
* Added pooler callback support.
* Broadcasting expiry of events.

<br/>

### Isolated changes
* Fixed: Changed the response code for User creation conflict case in CreateKernalUser API.
* Fixed: Changed the response code for Tenant activation conflict case in ActivateTenant API.
* Fixed: Changed the response code for CreateOnlineQr and Create OfflineQr API.

<br/>

### Configuration  Changes 
* Retry limit -5 (This Property will attempt to fetch the data based on the configured retry limit count).
* Retry interval - 3000ms (This property will be polling based on the configured milliseconds count).
* Default limit is 3 and interval is 1000 ms.

<br/>

### Bug Fixes
* Fixed: Issue in SetPassword API in updating the password in SSMS.
* Fixed: Changed the Uid response parameter key to UserID  in API’s - GetUserLogs and GetDeviceLogs.

<br/>

### Deprecation
* Callback url parameter in CreateActivationCode API. (Alternatively, use EventController. At Present, NEW DEVICE is added and available. in future, other events can be added).

<br/>

### Known issues
* Semantic errors with downloaded swagger json.

<br/>

### Not Supported
* AWS ElasticCache does not work with redis.
* Redis sentinal is not supported

<br/>

### SSMS Version
* 2.9.x supported
* 3.x not supported

<br/>

### Tested Server
* MultiTenant: Dev2
* SingleTenant: Delta

<br/>

### Dependencies
* **Docker Engine 19.03.8**
https://docs.docker.com/engine/release-notes/#19038
* **Docker Compose 1.25.5**
https://github.com/docker/compose/releases

<br/>

### Not Included in Package (Until final release)
Documentation under connector.aws1.kobil.com is not updated in this release.
Documentation available below is an inprogress stage, which will be improved in our upcoming releases until the final release.

