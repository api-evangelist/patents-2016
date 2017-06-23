---

title: Late binding authentication
abstract: A late-binding token (LBT) is securely generated and provided to a device application. When the LBT is presented and validated, a resource associated with the presentation is bound to the LBT and authenticated for access to a service and provided valid credentials for accessing that service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09654462&OS=09654462&RS=09654462
owner: NetIQ Corporation
number: 09654462
owner_city: Provo
owner_country: US
publication_date: 20160725
---
This application is a continuation of U.S. application Ser. No. 14 512 772 filed Oct. 13 2014 now issued as U.S. Pat. No. 9 401 912 which is incorporated herein by reference in its entirety.

Many mobile applications from different vendors may run on a single end user s device. To protect one application from other applications the mobile Operating System OS provides a sandbox for each application. The sandbox prevents direct memory access from one application to another. For example iOS APPLE S mobile OS blocks sharing of the KeyChain that is used to hold credentials and other secrets unless two applications are from a same vendor and are registered with APPLE with the same bundle identifier ID . This is a good features for security but a bad for Single Sign On SSO applications because there is no secure way to pass unprotected credentials from one application to another application so this limits SSO applications on iOS devices

Therefore there is a need for providing SSO capabilities on devices that attempt to control and limit the passing of credentials and secrets without comprising security on those devices.

Various embodiments of the invention provide techniques for late binding authentication. In an embodiment a method for late binding authentication is presented.

Specifically A request is received by a device for authenticating a resource for access to a service. Next a late binding token LBT is generated that is associated with the request. Then the LBT is sent to a second device associated with the resource. The resource is bound to the LBT upon receipt and validation of the LBT where the LBT is received back from the second device. Finally a message is communicated to the second device to indicate that the binding is completed and that the resource can now access and is now capable of authenticating to the service for access with a supplied valid authentication response.

A resource includes a user service system device directory data store groups of users files combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that at one time or another is an actor on another principal or another type of resource. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal. Resources can acquire and be associated with unique identities to identify unique resources during network transactions.

An identity is something that is formulated from one or more identifiers and secrets that provide a statement of roles and or permissions that the identity has in relation to resources. An identifier is information which may be private and permits an identity to be formed and some portions of an identifier may be public information such as a user identifier name etc. Some examples of identifiers include social security number SSN user identifier and password pair account number retina scan fingerprint face scan etc.

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X can be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment and the term cloud may be used interchangeably and synonymously herein.

Moreover it is noted that a cloud refers to a logical and or physical processing environment as discussed above.

Various embodiments of this invention can be implemented as enhancements within existing network architectures and network enabled devices.

Also the techniques presented herein are implemented in and reside within machines such as processor s or processor enabled devices hardware processors . These machines are configured and programmed to specifically perform the processing of the methods and system presented herein. Moreover the methods and system are implemented and reside within a non transitory computer readable storage media or machine readable storage medium and are processed on the machines processors configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension of particular embodiments only and is not intended to limit other embodiments of the invention presented herein and below.

It is within this context that embodiments of the invention are now discussed within the context of the .

The components presented are a mobile device phone laptop tablet wearable processing device etc. a NetIQ Mobile Application Server NMA and a Sales Force server.

The mobile device includes a Sales Force mobile app SFA and a NetIQ SSO mobile app app refers to application herein . The NMA includes an Identity Provider IDP and an Authentication Application Programming Interface API referred to as Auth API. The Sales Force server includes a Service Provider SP and an API service.

It will now be discussed how late binding authentication can occur on the mobile device for purposes of SSO using a late binding authentication token such that security is not compromised on the mobile device and such that even a mobile OS such as iOS can benefit from a SSO application such as the enhanced NetIQ app described below .

At 1 a user of the mobile device is using the SFA and that app needs to make an API call to the Sales Force API service. To do this the app must have a Sales Force OAuth token. So a token request is made from the SFA though an embedded browser.

At 2 the Sales Force server is configured to use Security Assertion Markup Language SAML for purposes of authenticating users. On receipt of the OAuth token request the embedded browser of the SFA is redirected to the NMA IDP with an SAML AuthN Request Part of the SAML protocol .

Next processing is enhanced for purposes of various embodiments of the invention presented herein and below. So at 3 the NMA IDP builds a Late Binding Token LBT . The LBT token can be created and built by the NMA IDP in a number of manners. As one example consider the following 1 a Unique Secure Random Number USRN is generated and large enough that it is not easily guessed by an intruder 2 a Time To Live TTL attribute is assigned to the USRN to indicate how long the USRN is valid for use 3 the provider ID of the requesting SP Sales Force in the present example is added 4 a relay state is include for anything that the NMA IDP wants to be returned and 5 a Hash based Message Authentication Code HMAC is generated for items 1 4 for ensuring data integrity of the LBT.

The component pieces 1 5 are combined and encrypted with a key that is known by the NMA IDP to form the LBT. At present the created LBT is without a user assignment and without user rights because a user of the mobile device is not yet known. The identity of the user and that user s rights are bound at a later point in time. This is particularly useful and beneficial as discussed herein. The USRN is prefilled into a hidden Hypertext Markup Language HTML form field that a JAVA script can automatically submit by the embedded browser of the SFA. HTML forms the Java script the LBT and a valid OAuth token are sent to the SFA.

At 4 the HTML forms and JAVA script are executed by the SFA embedded browser which then makes a call to the NetIQ app and passes the NetIQ app the LBT and the OAuth token. At this point in time the SFA processes in the background on the mobile device and the NetIQ app processes in the foreground on the mobile device after having been activated by the SFA.

At 6 the IDP validates the IDP OAuth token. Next the IDP decrypts the LBT and the HMAC is independently calculated and compared with the HMAC included with the LBT. The IDP then binds the user of the mobile device and access rights for the user defined by the IDP OAuth token to the LBT and then replies with a binding complete message to the NetIQ app on the mobile device.

At 7 the NetIQ app calls the SFA which causes the SFA to process in the foreground on the mobile device.

At 8 the SFA embedded browser sends the form containing the USRN to the IDP. The USRN is matched to the user defined in the LBT at 6 and the user is now authenticated to the IDP. Moreover because authentication was processed with the LBT the user does not need to re enter his her name and or password for authentication.

At 9 the SFA embedded browser is redirected to the SP of the Sales Force server with a valid SAML AuthN response.

At 11 the Sales Force OAuth token is then used to make authenticated Sales Force API calls to the Sales Force API service.

It is noted that the user of the mobile device is not prompted on the mobile device for user credentials and has access to protected resources of the Sales Force API service. Late binding authentication was achieved through the LBT to link the NetIQ app session to the SFA session. So the user authenticates once to the NMA server through the NetIQ app and does not need to do any additional authentication for using a different service such as the Sales Force service because the LBT and relevant processing described above allows SSO capabilities. This is a secure approach and is operational on OSs that restrict access to keys and credentials between competing applications within those OSs.

Moreover the techniques for late binding authentication for purposes of secure SSO can be used within any device authentication mechanism and or federation protocols. Such that the teachings presented herein are not limited to SAML OAuth a mobile device and or a Sales Force application which was shown for purposes of illustration of features that embodiments of the invention are capable of .

1 building a token that is bound at a later time to a user for purposes of late binding authentication through the LBT 

3 binding the LBT to a user or an object resource using a variety of authentication mechanisms OAuth SAML etc. after the LBT is built 

7 using an auto play and or JAVA mechanism to send the LBT at a fixed time and for a repeated interval 

8 allowing a variety of user display devices to send the LBT such as via nodes Ajax and other mechanisms 

9 providing SSO capabilities on a mobile device by sharing a session from one application with that of another application even when the OS for the mobile device does not provide such a mechanism for session sharing and

Aspects of the embodiments discussed above and other embodiments are now presented with the discussion of the .

In an embodiment the late binding authenticator interacts with one or more mobile apps on a mobile device operated by a user. The mobile device is one of a phone a tablet a phablet a laptop a wearable processing device.

In an embodiment the late binding authenticator interacts with one or more application on a desktop computing device.

In an embodiment the late binding authenticator performs the processing of the IDP and or the Auth API of the NMA server described above with reference to the .

At the late binding authenticator receives a request for authenticating a resource for access to a service. It is noted that the late binding authenticator processed on a device which is different from the device associated with the resource and which is different from the device associated with the service. In an embodiment the device associated with the resource is a mobile device phone laptop tablet wearable processing device etc. .

According to an embodiment at the late binding authenticator receives the request from the service that the resource is attempting to obtain authenticated access to.

At the late binding authenticator generates a LBT that is associated with the request for access to the service. This was discussed in detail above with reference to the .

In an embodiment at the late binding authenticator creates the LBT to include a random number an identifier for the service and a HMAC produced over the random number and the identifier.

In an embodiment of and at the late binding authenticator adds a TTL attribute and a state description to the LBT and then updates the HMAC to be produced over the TTL attribute and the state description with the random number and the identifier.

At the late binding authenticator sends the LBT to a second device associated with the resource. In an embodiment the resource is a user. In an embodiment the resource is an automated process that executes on the second device. In an embodiment the second device is a mobile device. In an embodiment the second device is a desktop computing device.

According to an embodiment at the late binding authenticator hides at least a portion of the LBT in a hidden HTML form with a script sent to the second device. In an embodiment this is a random number associated with the LBT as discussed above with reference to the .

At the late binding authenticator binds the resource to the LBT upon receive and validation of the LBT the LBT is received back from the second device when it is ready to be used to authenticate the resource for access to the service.

In an embodiment at the late binding authenticator independently re generates at least a portion of the LBT and compares that portion with a corresponding portion included in the LBT to validate that the LBT was not tampered with. In an embodiment the re generated portion is an HMAC and the portion in the LBT is an HMAC.

In an embodiment at the late binding authenticator receives a credential for accessing the service with the LBT that is sent back from the second device when the resource is ready to be authenticated to the service.

In an embodiment of and at the late binding authenticator assigns access rights to the resource for accessing the service based on the credential.

In another embodiment of and at the late binding authenticator obtains the credential as an authentication token recognized by and perhaps issued by the service for access to the service.

At the late binding authenticator communicates a message to the second device that binding is complete and that the resource can access and is capable of authenticating to the service for access.

In an embodiment at the late binding authenticator uses the message to automatically trigger re sending by the second device a portion of the LBT and verifies that the portion is associated with the resource and further provides to the second device a valid authentication response for accessing the service when the portion is successfully verified. This scenario was discussed above with the at 8 and 9.

In an embodiment the SSO client agent at least partially performs the processing of the NetIQ app of the .

At the SSO client agent requests an access session with a remote service of a second device. This can be driver by a resource that is a user accessing an application on the device that executes the SSO client agent which requires authentication of the user.

In an embodiment at the SSO client agent obtains the authentication token as a token that was generated by the remote service.

In an embodiment of and at the SSO client agent obtains the LBT as a second token that is generated by an identity provider discussed below at .

At the SSO client agent sends to an identity provider associated with a third device a resource identifier for a resource requesting access to the service the authentication token and the LBT. This is an indication that the resource of the device associated with the SSO client agent is ready to be authenticated to the remote service for access to the session with the remote service.

In an embodiment at the SSO client agent provides the resource identifier as a particular resource that is already authenticated to the identity provider from the device for SSO services.

At the SSO client agent obtains from the identity provider a message indicating that the LBT for the resource is bound to the authentication token.

In an embodiment at the SSO client agent automatically sends at least a portion of the LBT back to the identity provider to confirm the resource is authenticated to the identity provider.

In an embodiment of and at the SSO client agent initiating a script embedded in a HTML form upon receipt of the message to locate the portion of the LBT which is in a hidden field. The SSO client agent then sends the portion to the identity provider.

At the SSO client agent acquires a valid authentication response from the identity provider for the resource to participate in the access session with the service and as an authenticated resource.

In an embodiment at the SSO client agent redirects a browser being operated by the resource on the device to the access session with the valid authentication response.

According to an embodiment the late binding authentication system implements in whole or in part and inter alia various features of the . Thus all processing discussed above with respect to the prior FIGS. are incorporated by reference herein with respect to the late binding authentication system and the discussion of the .

The processor is part of a device that is remotely located over a network from a user operated device mobile or desktop computing device .

In an embodiment the processor is part of a cloud machine associated with a cloud processing environment.

The late binding authenticator is adapted and configured to execute on the processor and provide authentication of a resource authenticated to the late binding authenticator with authentication credentials to a service using a LBT when the resource requests access to the resource.

In an embodiment the late binding authenticator is the IDP and or Auth API of the NMA server of the .

In an embodiment the late binding authenticator is further adapted and configured to interact with one or more applications processing on a device associated with the resource and to interact with one or more other applications processing on a second device associated with the service. The processor is on a third device that is different from the device associated with the resource and also different from the second device associated with the service.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

