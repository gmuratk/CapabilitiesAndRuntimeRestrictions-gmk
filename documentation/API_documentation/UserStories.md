
**User Story: Capabilities and Runtime Restrictions - Query**
<br>

| **Item** | **Details** |
| ---- | ------- |
| ***Summary*** | As an application developer, I want my application to comply with current restrictions applicable based on the service status, network conditions, and location |
| ***Roles, Actors and Scope*** | **Roles:** Customer:User<br> **Actors:** Mobile Network Operators (MNO), [Entprerise] Application developers. <br> **Scope:** Any device serviced by MNO|
| ***Pre-conditions*** |The preconditions are listed below:<br><ol><li>Application developer has been onboarded to MNO</li><li>MNO offeres Capabilities and Runtime Restrictions APIs</li><li>Application developer has subscribed to Capabilities and Runtime Restriction APIs</li><li>As necessary, customer consent has been secured</li><li> Application developer has implemented Capabilities and Runtime Restriction API</li></ol>|
| ***Activities/Steps*** | **Starts when:** Presumably upon mobile application client session start. Application makes a request to retreieve the list of capabilities, their status (enabled/disabled), and restrictions that are applicable to those enabled services, given a particular client.  <br> **Ends when:** MNO returns the capabilities and runtime restrictions applicable to the request.|
| ***Post-conditions*** |<ol><li>Application may adjust UI elements according to the current restrictions.  The Application, when sending a request to the CAMARA API, can ensure / adjusts information according to the restrictions.</li><li> MNO may maintain a cache of the capabilities and restrictions sent in response to Application request.</li></ol>|
| ***Exceptions*** | Several exceptions might occur:<br><ul><li> Unauthorized: Not valid credentials</li> Not found: Client identifier is not managed by the MNO</li><li> Invalid Input: Request is not properly structured, or missing mandatory input data</li><li> Service not available: Capabilities and Runtime Restrictions service is [temporarily] not available</li></ul>|

<br><br>

**User Story: Capabilities and Runtime Restrictions - Subscription**
<br>

| **Item** | **Details** |
| ---- | ------- |
| ***Summary*** | As an application developer, I want my application to comply with current restrictions applicable based on the service status, network conditions, and location.  I want my application to subscribe to any changes in capabilities and restrictions |
| ***Roles, Actors and Scope*** | **Roles:** Customer:User<br> **Actors:** Mobile Network Operators (MNO), [Entprerise] Application developers. <br> **Scope:** Any device serviced by MNO|
| ***Pre-conditions*** |The preconditions are listed below:<br><ol><li>Application developer has been onboarded to MNO</li><li>MNO offeres Capabilities and Runtime Restrictions APIs</li><li>Application developer has subscribed to Capabilities and Runtime Restriction APIs</li><li>As necessary, customer consent has been secured</li><li> Application Client or the Application Backend server has implemented Capabilities and Runtime Restriction API</li></ol>|
| ***Activities/Steps*** | **Start when:** Presumably upon mobile application client session start. Application  makes a request to receive the current the list of capabilities, their status (enabled/disabled), and restrictions that are applicable to those enabled services and subscribe to any changes after the intial push. <br> **Continues with:** <ul><li>Any changes in capabilities or runtime restrictions change sent as an event notification to subscribed Application</li><li>Application may adjust UI elements according to the current restrictions.  The Application, when sending a request to the CAMARA API, can ensure / adjusts information according to the restrictions.</li></ul> **Ends when:** Subscrption expires, or subscribing entity terminates the subscription|
| ***Post-conditions*** |<ol><li> MNO may maintain a cache of the capabilities and restrictions responded with.</li><li>Application client may enable/disable UI components based on restricted services at time.</li><li>Application client validates, localy or with the Application backend server, Service API prior to making a request to the MNOs Service API endpoint, and avoids any failures.</li></ol>|
| ***Exceptions*** | Several exceptions might occur:<br><ul><li> Unauthorized: Not valid credentials</li> Not found: Client identifier is not managed by the MNO</li><li> Invalid Input: Request is not properly structured, or missing mandatory input data</li><li> Service not available: Capabilities and Runtime Restrictions service is [temporarily] not available</li></ul>|
