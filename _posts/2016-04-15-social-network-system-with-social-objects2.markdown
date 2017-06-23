---

title: Social network system with social objects
abstract: A social network system provides a social network that receives from an application a business object and an associated system of record and generates a social object that corresponds to the business object and that comprises the system of record for the enterprise application. The social network assigns one or more members to the social object. The social network receives first changes to the system of record and, in response, modifies the social object to incorporate the first changes. The system provides second changes to the social object to the enterprise application, and the enterprise application, in response, modifies the system of record to incorporate the second changes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09626728&OS=09626728&RS=09626728
owner: Oracle International Corporation
number: 09626728
owner_city: Redwood Shores
owner_country: US
publication_date: 20160415
---
This application is a continuation application of U.S. application Ser. No. 13 622 071 filed on Sep. 18 2012 which claims priority of Provisional Patent Application Ser. No. 61 640 913 filed on May 1 2012 the contents of each which is hereby incorporated by reference.

One embodiment is directed generally to a networked computer system and in particular to a social network system with social objects.

A social network service or system or social network is an online service platform or site that focuses on facilitating the building of social networks or social relations among people who for example share interests activities backgrounds or real life connections. A social network service typically includes a representation of each user typically referred to as a user profile his her social links and a variety of additional services. Most social network services are web based and provide means for users to interact over the Internet such as e mail and instant messaging. Social networking sites allow users to share ideas activities events and interests within their individual networks.

The use of social network services in an enterprise business context is increasingly becoming more popular. Because social networks connect people at low cost they can be beneficial for entrepreneurs and small businesses looking to expand their contact bases. These networks often act as a customer relationship management tool for companies selling products and services. Companies can also use social networks for advertising in the form of banners and text ads. Since businesses operate globally social networks can make it easier to keep in touch with contacts around the world.

One embodiment is a social network system that provides a social network that receives from an application a business object and an associated system of record and generates a social object that corresponds to the business object and that comprises the system of record for the enterprise application. The social network assigns one or more members to the social object. The social network receives first changes to the system of record and in response modifies the social object to incorporate the first changes. The system provides second changes to the social object to the enterprise application and the enterprise application in response modifies the system of record to incorporate the second changes.

One embodiment is a social network system that creates social objects that correspond to business objects from enterprise business applications. The social object includes a wall that displays changes to the system of record of the business object. Multiple conversations for a single social object can be related to the social object and can be stored and accessed at a future date.

Social network server system in conjunction with the other devices of substantially provides the functionality of a social network with social object conversations related to a social object as disclosed in more detail below. Social network server is coupled to an enterprise application server . Enterprise application server in one embodiment is a server or servers that execute enterprise applications such as human resource HR applications customer relationship management CRM applications enterprise resource planning ERP applications etc. In one embodiment the enterprise applications on server are the E Business Suite or Fusion applications from Oracle Corp. Server can be directly coupled to server can be coupled in any other way such as over a network. In addition the functionality of server can be included on server . Further server can be coupled to clients directly through a network or other means rather than through server . Server is generally not part of social network but provides the business objects and system of records that are used to generate social objects.

Computer readable media may be any available media that can be accessed by processor and includes both volatile and nonvolatile media removable and non removable media and communication media. Communication media may include computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media.

Processor is further coupled via bus to a display such as a Liquid Crystal Display LCD . A keyboard and a cursor control device such as a computer mouse are further coupled to bus to enable a user to interface with system .

In one embodiment memory stores software modules that provide functionality when executed by processor . The modules include an operating system that provides operating system functionality for system . The modules further include a social network module for providing social network functionality as disclosed in more detail below. System can be part of a larger system such as an ERP system if that functionality is not already provided by server of . Therefore system can include one or more additional functional modules to include the additional functionality. A database is coupled to bus to provide centralized storage for modules and and store data such as user profiles social objects conversations etc. Storage of these items can also be done remote from system .

In one embodiment social network of is a secure enterprise collaboration and social network software application and platform designed to facilitate social interactions within the enterprise environment as opposed to a consumer environment connecting people applications and business processes within and across businesses. Social network includes user profiles conversations and social objects .

A conversation in social network in one embodiment is a persistent shared stream of posts and comments i.e. messages including for example text rich text documents audio video programmatic content referred to as gadgets etc. A conversation has a defined membership ranging from Private i.e. membership of one self through N members consisting of individuals and or groups of individuals or sub groups to Public with visibility open across all members of social network . Posts within a conversation are viewed with new posts beneath old posts i.e. multiple posts can be read as text on a page in a book or vice versa or in any type of hierarchical format.

One embodiment generates social objects. All data from enterprise applications and business processes can potentially be socialized as a social object. Social objects contain records from a business application or process referred to as a system of record that are mapped as a visual and programmatic integration into social network via social network server . For example a sales opportunity from within a CRM enterprise application e.g. the name of a sales prospect and related data for the sales prospect such as the estimated probability that a sale will close the expected revenue of the sale etc. is integrated into social network as a social object. As a result social objects are explicitly coupled with conversations where the social object can be discussed in context and a record of that discussion can be retained for future viewing.

A set of programmatic rules defining the behavior of the integration and actions on receiving business events from the object within the system of record i.e. the business object in the enterprise application .

A wall i.e. a stream of posts displaying publication of changes in the data set of the associated object from within the system of record and status posts from members users of social network with appropriate access rights. The wall provides an activity stream holding short sometimes unrelated posts in which old information may scroll off the bottom of the list. The wall differs from a conversation in which all content is related.

A set of related conversations or other social objects e.g. a Customer social object can be related to multiple Opportunity social objects .

A membership potentially defined controlled and managed by the system of record or open to sharing across the network with individuals and groups.

A gadget storing data from the associated object within a system of record allowing quick access and updates to the original data set within the system of record e.g. the revenue value of a CRM opportunity is displayed within a gadget and a member with access to the corresponding opportunity social object and the appropriate access rights within the system of record can update the revenue value in the system of record from the gadget tied to the social object within social network .

A social object may be generated for social network for any business object of an application that users may desire to collaborate on over social network . Examples of social objects include 1 an Opportunity social object from a CRM application 2 a Customer social object from a CRM application 3 a Service Request social object from a CRM application 4 a Business Process Shipment Escalation social object from a business process application 5 a Portal subject social object from a web portal application 6 a General Ledger Period Close social object from a financial ERP application 7 an Inventory Item social object from an inventory ERP application and 8 an Ordered Product social object from a distributed order orchestration application e.g. Fusion Distributed Order Orchestration DOO application from Oracle Corp. .

In one embodiment a conversation for social network can be created for any collaborative purpose including having a specific discussion making a decision or resolving a problem. A conversation can be related to a social object. The conversation can have membership which is identical a superset or a subset of the social object membership. For example a conversation can be created that is related to a sales opportunity social object in which the sales team works on preparing the presentation for the customer. A second related conversation can be created in which only the sales lead works with the legal team in reviewing contractual changes requested by the customer. Through related conversations multiple parallel threads of work between different constituent parties all related to the changing of state of an object within the system of record e.g. the opportunity changes from a state of Negotiation to a state of Won is achieved while maintaining the relationship understanding and contextual persistent of the collaboration that drove the changes. For example related conversations for an Opportunity social object may include a conversation for preparing a presentation with the suggested presentation content and best practice notes for delivery and a conversation for finalizing the contract with the appropriate draft contract for the deal size industry product and sales region with the associated legal team member added. A social object can also be related to another social object.

Social object further includes a wall that shows a history of all of the changes that have occurred on the social object. For example at the win probability is shown to have been updated by Julian Henderson from 50 to 60 on May 14 2012 at 11 44 a.m. At a new member Charles Dreyfus was given access to the social object on May 14 2012 at 11 43 a.m.

Social object further includes a list of all members of the social object at . The members who are currently online for that social object e.g. member are shown with a typical thumbnail picture but members who are currently offline e.g. member are shown as a grayed out thumbnail picture.

Social object further includes a list of all conversations related to social object at . A user can view one of the conversations by selecting the conversation. In one embodiment social object and new related conversations such as related conversations are created when the user is interacting with the external or third party enterprise system such as a CRM or ERP system executing on for example server of . For a given business object within a system of record of an enterprise application a social object and a customized set of related conversations with content can be created programmatically e.g. as a pre defined template to assist with the collaboration required to change the state of the system of record. In one embodiment an application programming interface API from the enterprise application to the social network application allows changes in the system of record to be communicated to the social network system and vice versa. A selectable list of other social objects that are related to social object can also be displayed.

In the example of tab is selected to generate a conversation. However because the object is not yet shared a message indicates that the object is not yet shared and a Share button is provided to share the object. Sharing the object causes a social object to be generated that corresponds to business object . An API to social network server and social network is used to generate the social object.

At social network module receives from an application a business object and associated system of record. In one embodiment the application is an enterprise application such as a CRM or ERP application. An example of a system of record for a business object is shown in section of . An API to social network server and social network of is used to receive the business object.

At social network module generates a social object that corresponds to the business object and that comprises the system of record. An example of a social object is social object of in which the system of record is shown in section .

At social network module assigns one or more members to the social object. An example of assigned members are members of social object of .

At social network module associates a wall to the social object. The wall displays changes to the system of record. An example of a wall is wall of social object of .

At the social object is displayed assuming it has been created with the system of record. For example as shown in social object is displayed within the system of record for data storage replacement opportunity.

At it is determined if there are any existing conversations for the social object. If no at a conversation is created at . The new conversation at is automatically related to the social object.

If conversations exist the conversation is selected at and the conversation is then related to the social object at .

The functionality of can be performed within an enterprise application as shown in or within social network . An API to social network server and social network is used to provide the integration of .

As disclosed social network allows a social object to be generated and one or more conversations can be related to the social object. The social object is a set of properties tied to a wall. These properties are directly connected to the object in the system of record and are updated either when they are changed in the system of record directly or through actions in social network . Changes made within social network are pushed back to the system of record to keep the object s properties current at all times. All changes can be logged on the wall and related conversations can easily be created to discuss specific issues concerning the social object. The social object can be exposed through any type of applications including the web client Outlook from Microsoft Corp. or other email applications standalone embeddable clients and all mobile clients.

Social network includes a set of predefined integration mechanisms that enable the user to define how and what data is retrieved from the system of record how to display that data in social network for example through social objects and who within social network has access to the data.

These predefined mechanisms are built to handle the most common application chores such as specifying membership lists in social network and property sensitivity i.e. not everyone should be able to see or update all properties without authorization and updating properties in both directions. For example when a social object property is updated in the system of record that change is published in social network based on the user permission rules that the user has defined.

Social objects are defined in social network as records within a system of records such as customer or service records from a CRM system. Social object records include metadata and a wall which includes membership lists and related conversations. Social objects expose system of record information to users who interact with and collaborate around the data through a user interface of social network .

The social objects provide a uniform and collaborative view of information from all integrated systems of record. The social objects provide a wide range of services and capabilities in one embodiment including 

Displaying select metadata needed for collaboration via an extensible gadget usually visible as part of a wall 

Receiving a data stream of important activities fed by an activity stream or a web service from a system of records 

Enabling users to post messages create follow ups and easily catch up with activity through persisted and related conversations 

As an example of the functionality of a social object after a CRM Opportunity social object retrieves a stream of data input from the social object s wall the process may unfold as follows 

2. The new information is shared with a broader group of individuals who provide more context to the Opportunity.

3. Users not directly tied to the CRM Opportunity team can now interact and react to the Opportunity s status. For example if the Opportunity is won that may be the Service organization s cue to take over and begin the implementation process. The Service organization can then publish that information on the Opportunity s Wall.

Communication also works in the other direction. When the Opportunity is updated from within social network the change is reflected in the system of record as well. Before the change is made social network checks to ensure that the user has the right to update the object from changing a simple property to changing the state of the object for example from Pending to Won . There is no need to go back into CRM to update key fields as social network automatically provides the updates.

Therefore as disclosed embodiments generate social objects related to enterprise application business objects and systems of record. Multiple conversations related to the social objects with potentially varied membership can be created and stored for future reference. Further updates to social objects are automatically reflected in corresponding business objects and vice versa.

Several embodiments are specifically illustrated and or described herein. However it will be appreciated that modifications and variations of the disclosed embodiments are covered by the above teachings and within the purview of the appended claims without departing from the spirit and intended scope of the invention.

