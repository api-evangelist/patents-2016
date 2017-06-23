---

title: Information processing system, apparatus, and method
abstract: An information processing system includes first and second information processing apparatuses. The first information processing apparatus transmits a request for status notification to the second information processing apparatus, which transmits a response of the status notification to the first information processing apparatus. The second information processing apparatus transmits a header of the response to the first information processing apparatus when receiving the request for the status notification from the first information processing apparatus, and transmits a part of a body of the response to the first information processing apparatus in response to the occurrence of a status change to be reported in the second information apparatus. The part of the body includes information on the status change. The second information processing apparatus transmits a last part of the body of the response to the first information processing apparatus when the status notification becomes unnecessary.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09639307&OS=09639307&RS=09639307
owner: Ricoh Company, Ltd.
number: 09639307
owner_city: Tokyo
owner_country: JP
publication_date: 20160126
---
The present application is a continuation of U.S. patent application Ser. No. 14 571 494 filed on Dec. 16 2014 which is based upon and claims the benefit of priority of Japanese Patent Application No. 2013 265730 filed on Dec. 24 2013. The disclosures of the prior applications are hereby incorporated herein in their entirety by reference.

Web application program interfaces Web APIs of a style called SOAP Simple Object Access Protocol or REST Representational State Transfer are often used for providing various services on the Web Web services . Web APIs are based on communications by HTTP Hypertext Transfer Protocol . Service providers operate as HTTP servers to provide Web APIs while service users operate as HTTP clients to use the Web APIs.

On the other hand examples of information processing systems or information processing apparatuses include image forming apparatuses such as laser printer LP s and multifunction peripheral or multifunction printer MFP s. According to these types of image forming apparatuses an operation part that displays a screen and performs key input operations is provided independent of a body part a controller and an engine so as to avoid a decrease in operational response even when the operational load on the body part is high. The operation part is provided with an independent operating system OS such as Android registered trademark and operates independent of the body part.

In image forming apparatuses also provided with such an operation part the above described REST style Web APIs may be used and an application application program on the operation part implements functions using a Web API provided by the body part.

Common HTTP communications are based on a configuration where a server returns a response to a request from a client. Therefore according to the architecture of HTTP communications it is impossible in principle to notify a client of changes in status events that occur at random times on the server side.

A number of techniques for notifying changes in status that occur on the server side have been discussed. As a typical technique a technique called polling according to which a client queries a server at regular intervals to check changes in the status of the server is commonly known.

Furthermore techniques such as Ajax Asynchronous JavaScript registered trademark XML Extensible Markup Language LongPolling and Comet are commonly known as measures for emulating notifying a client of changes in the status of a server.

According to an aspect of the present invention an information processing system using a protocol according to which a session with respect to a single request is completed by returning a predetermined response to the single request includes a first information processing apparatus and a second information processing apparatus. The first information processing apparatus transmits a request for status notification to the second information processing apparatus and the second information processing apparatus transmits a response of the status notification to the first information processing apparatus. The second information processing apparatus includes a processor and a memory storing instructions that when executed by the processor causes the second information processing apparatus to transmit a header of the response of the status notification to the first information processing apparatus in response to receiving the request for the status notification from the first information processing apparatus transmit a part of a body of the response of the status notification to the first information processing apparatus in response to occurrence of a status change to be reported in the second information apparatus the part of the body including information on the status change and transmit a last part of the body of the response of the status notification to the first information processing apparatus in response to the status notification becoming unnecessary.

According to an aspect of the present invention an information processing apparatus of an information processing system using a protocol according to which a session with respect to a single request is completed by returning a predetermined response to the single request wherein another information processing apparatus transmits a response of the status notification to the information processing apparatus includes a processor and a memory storing instructions that when executed by the processor causes the information processing apparatus to transmit a request for status notification to the other information processing apparatus of the information processing system receive a header of the response of the status notification transmitted from the other information processing apparatus in response to the request for the status notification receive a part of a body of the response of the status notification transmitted from the other information processing apparatus in response to occurrence of a status change to be reported in the other information processing apparatus the part of the body including information on the status change and receive a last part of the body of the response of the status notification transmitted from the other information processing apparatus in response to the status notification becoming unnecessary.

According to an aspect of the present invention an information processing method executed by an information processing apparatus of an information processing system using a protocol according to which a session with respect to a single request is completed by returning a predetermined response to the single request wherein another information processing apparatus transmits a response of the status notification to the information processing apparatus includes transmitting a request for status notification to the other information processing apparatus of the information processing system receiving a header of the response of the status notification transmitted from the other information processing apparatus in response to the request for the status notification receiving a part of a body of the response of the status notification transmitted from the other information processing apparatus in response to occurrence of a status change to be reported in the other information processing apparatus the part of the body including information on the status change and receiving a last part of the body of the response of the status notification transmitted from the other information processing apparatus in response to the status notification becoming unnecessary

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and not restrictive of the invention.

As described above a number of techniques for reporting changes in a server status from an HTTP server to an HTTP client have been devised. The techniques however have respective problems and restrictions as follows.

Polling refers to detecting changes in the status of a server by periodically querying the server about its status by a client. Accordingly the timing realtimeness of detection of changes in the server status depends on the client process.

For example a client periodically polls a server transmits a status notification request to and receives a response from a server at times t t t and so on. In this case if the status of the server changes between time t and time t there is a delay before the status change is detected by polling at time t thus lacking in realtimeness.

Ajax is a technique for performing asynchronous communications between a Web browser and a server. Here the term asynchronous means the absence of synchronism with the updating of a browser screen. Communications between a Web browser and a server used to be possible only in synchronism with the updating a browser screen. Therefore Ajax has been developed as a technique for communicating asynchronously with a browser screen.

Ajax however does not differ greatly from polling in that a server status can only be returned at the time of a client s request in client server communications.

Comet and LongPolling are techniques according to which a server returns no response before the occurrence of a change in the server status when polled by a client. It is possible for the server to respond in real time in accordance with changes in the server status by maintaining the connection with the client. See for example Japanese Laid Open Patent Application No. 2011 232893. 

According to these techniques however the client and the server are disconnected once the server responds to the client. Therefore when it is required to continue to detect changes in the server status the client is required to poll the server again. Therefore if the server status changes in an extremely short period of time the change may not be detected.

For example when a client polls a server at time t the server waits until a status change occurs. When a status change occurs at time t the server notifies the client of the status change. The communication however ends by this notification of the status change response . Therefore if another status change subsequently occurs in the server immediately after the end of the communication it is not possible for the client to detect the subsequent status change by polling the server again at time t.

According to an aspect of the present invention it is ensured that changes in the status of an information processing apparatus operating as a server are reported in real time to an information processing apparatus operating as a client.

A description is given below with reference to the accompanying drawings of one or more embodiments of the present invention. In the following a description is given taking an image forming apparatus as an example of an information processing system or apparatus. Embodiments of the present invention however may also be applied to information processing systems or apparatuses other than the image forming apparatus.

Referring to an image forming apparatus such as an MFP includes a body part controller and engines and an operation part . The operation part has a wired or wireless connection to the body part .

The body part has the function of converting print data from a host computer such as a personal computer PC or a server into video data and outputting the video data to a printer engine in accordance with a control mode set at the time and a control code from the host computer . Furthermore the body part has the function of reading an original image by a scanner engine and making a copy of the read image by outputting the read image to the printer engine or outputting the read image to the host computer .

The operation part is a computer unit that includes a touchscreen and its own OS along with a central processing unit CPU and a memory.

The body part includes a CPU a random access memory RAM a nonvolatile RAM NV RAM a program read only memory ROM a font ROM a network interface an operation part interface a printer engine interface a scanner engine interface a hard disk drive HDD an option RAM the printer engine and the scanner engine .

The RAM is used as a work memory when the CPU executes processes. The RAM is also used as a buffer for managing and temporarily storing data from the host computer page by page and as a bitmap memory for storing video data actual print patterns into which data stored in the buffer are converted.

The NV RAM is a nonvolatile RAM for storing data that are desired to be retained even after power is turned off.

The program ROM contains programs for managing data inside the body part and controlling peripheral modules.

The network interface is an interface for control signals and data from the host computer to the image forming apparatus and status signals data from the image forming apparatus to the host computer .

The operation part interface is an interface for control signals and data between the body part and the operation part .

The printer engine interface is an interface for control signals and data to the printer engine and status signals from the printer engine .

The scanner engine interface is an interface for control signals to the scanner engine and status signals and data from the scanner engine .

The printer engine forms and develops an electrostatic latent image on a photoconductor based on a video signal and a control signal provided via the printer engine interface feeds transfer paper from a paper feeding part and forms an image on the transfer paper by transferring and fixing the developed image onto the transfer paper.

The scanner engine optically reads original material such as a document and outputs image information.

Referring to multiple host computers A B and C and the image forming apparatus are interconnected by a communication medium .

The image forming apparatus includes the body part and the operation part . The operation part is in direct wired or wireless connection to the body part . Alternatively the operation part may be connected to the body part via an access point not illustrated on the network. An application on the operation part implements functions of the application using a Web API provided by the body part .

It is possible for the host computers A B and C which may be hereinafter collectively referred to as the host computer to make a request for printing to the image forming apparatus and receive read images of original material from the image forming apparatus and to use Web services using Web APIs provided by the image forming apparatus the body part .

Referring to the body part includes a network management module a Web service providing module a print management module a system management module and a memory management module which form a service providing module group . Furthermore the body part includes a printer job management module a copy job management module and a scanner job management module which use the functions of the modules through of the service providing module group . Furthermore the body part includes a PDL analysis module used by the printer job management module .

The operation part includes operation part applications and . The operation part applications through operate on the operation part . Applications having various functions may be developed using JAVA registered trademark the Android registered trademark SDK or APIs independently provided by the body part . The number of operation part applications is not limited to three as illustrated in and may be one two or four or more. Here it is assumed that the operation part applications through operate as clients of Web services.

The PDL analysis module of the body part is a module that analyzes PDL data that the image forming apparatus receives from the host computer and generates a print image. The PDL analysis module receives PDL data from the printer job management module and generates a print image on memory reserved from the memory management module through the intermediation of the printer job management module . Furthermore the PDL analysis module obtains apparatus configuration information for example information such as the configuration of paper feeding trays and paper ejection trays and the sizes of paper in paper feeding trays which is used at the time of generation of print images from the system management module through the intermediation of the printer job management module .

The printer job management module performs general control of PDL processing. The printer job management module is a module that mediates processes required by the PDL analysis module and makes requests to other modules. For example the printer job management module mediates the transfer of PDL data received by the network management module to the PDL analysis module mediates the acquisition of apparatus information managed by the system management module by the PDL analysis module mediates the reservation of required memory from the memory management module by the PDL analysis module and issues print requests to the print management module with respect to print images created by the PDL analysis module .

The copy job management module performs general control of copy processing. The copy job management module implements a copy function using the service providing module group .

The scanner job management module performs general control of scan processing. The scanner job management module implements a scanner function using the service providing module group .

The network management module is a module that manages a network controller not illustrated and controls the processing of received data obtained from the network controller. The network management module receives data from the network controller by controlling communications protocols such as FTP file transfer protocol and LPR line printer remote protocol that are used to receive data from the host computer and transfers the received data to other modules. In providing Web services the network management module receives data by HTTP REST access from clients and transfers the received data to the Web service providing module .

The Web service providing module is a module that operates as an HTTP server for REST and SOAP and provides Web services to clients. The Web service providing module cooperates with other modules in the image forming apparatus in order to provide various functions as Web services. For example the Web service providing module cooperates with the printer job management module in order to provide a printer print function. Furthermore the Web service providing module cooperates with the copy job management module and the scanner job management module so as to provide a copy function and a scanner function as Web services. Although not illustrated in the drawings the Web service providing module may provide a facsimile function as a Web service by cooperating with a module that implements the facsimile function. The Web service providing module receives requests from HTTP clients transmits a response to HTTP clients and serializes and deserializes JSON JavaScript Object Notation data included in messages transferred between a server and a client.

The print management module is a module that performs control related to the printing of print images generated by the PDL analysis module . The print management module executes various processes for causing the printer engine to perform printing of print images stored in a memory or an external storage device managed by the memory management module . The print management module issues a paper feeding or ejection command issues a post processing execution command and detects a printing related error situation and reports the detected error situation to other modules.

The system management module is a module that manages and controls the apparatus configuration information and the apparatus condition of the image forming apparatus . The apparatus configuration information includes information on the attachment and detachment of paper feeding trays and paper ejection trays and information on paper arrangement in paper feeding trays. The apparatus condition refers to the operating state of the image forming apparatus such as printing waiting or suspending due to the occurrence of an error such as a paper jam or the absence of paper. In addition to reporting such information to other modules the system management module manages user provided apparatus settings such as customizable items that are variably set to change operations .

The memory management module is a module that manages a memory and an external storage device. The memory management module allocates or frees memory or an external storage device based on other modules requests.

The service providing module group refers to a collection of modules that provide various kinds of services. The modules of the service providing module group communicate with one another so as to share in performing the basic operations of the image forming apparatus and cooperate to respond to requests from an upper layer.

Referring to at step S the host computer operating as an HTTP client transmits an HTTP request for execution of printing to the image forming apparatus and the network management module of the body part receives the HTTP request. For example a uniform resource identifier URI such as printer job is specified in the HTTP request for execution of printing to be transmitted.

In response to the reception of the HTTP request at step S the network management module transmits a request for execution of printing to the Web service providing module .

At step S the Web service providing module notifies a module corresponding to the request to execute processing. In this example the Web service providing module transmits a request for execution of printing to the printer job management module . To be more specific by registering a URI and an event handler corresponding to the URI at the time of for example activation the Web service providing module determines a transfer destination module and transmits a request to the determined module.

At step S the printer job management module analyzes a header and a body included in the request for execution of printing and at step S requests the PDL analysis module to generate an image.

In response to reception of a response indicating the completion of image generation from the PDL analysis module at step S at step S the printer job management module instructs the print management module to execute printing.

In response to reception of the completion of printing from the print management module at step S at step S the printer job management module notifies the Web service providing module of the result as a response.

Likewise at step S the Web service providing module transmits a response to the network management module . Eventually at step S an HTTP response is transmitted to the host computer that is an HTTP client.

Here a print execution process in the printer is illustrated by way of example. Other functions also are implemented by the Web service providing module notifying corresponding modules to execute processing.

Referring to at step S the operation part application of the operation part which operates as an HTTP client transmits an HTTP request for status notification to the body part and the network management module receives the HTTP request. A session is established between the operation part application and the network management module by the HTTP request for status notification by the operation part application .

In response to the reception of the HTTP request at step S the network management module transmits a request for status notification to the Web service providing module .

The Web service providing module transmits a request for status notification to modules that manage statuses to be reported. Here at step S the Web service providing module transmits a request for status notification to the printer job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the copy job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the scanner job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the system management module .

Furthermore at step S the Web service providing module transmits an initial response that includes no status notification to the network management module .

In response at step S the network management module transmits a header only HTTP response to the operation part application . This HTTP response is not complete as a normal HTTP response so that the session remains maintained.

Thereafter for example when the printer job management module detects a status change at step S the printer job management module transmits a response reporting the status change to the Web service providing module .

In response at step S the Web service providing module notifies the network management module of the status change as part of the response.

In response at step S the network management module transmits an HTTP response including the data of the status change as part of the body to the operation part application .

Thereafter when any of the printer job management module the copy job management module the scanner job management module and the system management module detects a status change an HTTP response including the data of the status change as part of the body is transmitted to the operation part application through the Web service providing module and the network management module .

Furthermore when there is no status change to report to the operation part application for a predetermined time at step S the Web service providing module notifies the network management module of the absence of a status change as part of the response when the predetermined time elapses in order to prevent the session from being closed by the occurrence of a timeout on the operation part application side.

In response at step S the network management module transmits an HTTP response including the data of the absence of a status change as part of the body to the operation part application .

Then when status notification becomes unnecessary at the time of for example turning off the body part at step S the Web service providing module transmits a final response that completes the session to the network management module .

At step S the network management module transmits an HTTP response of the last part of the body to the operation part application . As a result an HTTP response corresponding to the initial HTTP request step S is completed so that the session is closed.

Thus the session is maintained after the HTTP request for status notification from the operation part application until status notification becomes unnecessary and during this period in response to detection of status changes the status changes are reported by divisional responses into which a response is divided . Therefore it is possible to report every status change in real time.

Web services are based on the idea that a server and a client exchange information by HTTP communications.

According to the protocol of HTTP communications the basic principle is that an HTTP client always issues an HTTP request and a server responds to the HTTP request. Typically when the server transmits an HTTP response in response to the HTTP request from the HTTP client the processing of the request is completed and thereafter the server is prevented from transmitting information to the HTTP client before the HTTP client issues another HTTP request.

Therefore the HTTP response is divided and transmitted in order to prevent the processing of the request from being completed by the HTTP response from the server. is a diagram illustrating the relationship between the divided response and HTTP data.

An HTTP client that desires to detect a status change of a server transmits an HTTP request for status notification to the server. The server first returns only a header portion in response to the establishment of a connection with the HTTP client. Normally a Content Length indicating a data size is commonly described in the header. In this case however the size of data to be returned is not known beforehand. Accordingly the header is returned with no description of a Content Length. Including no Content Length in the header is not a problem in terms of HTTP specifications.

Thereafter a body portion is not transmitted before there is a status change of the server. The HTTP client waits for a response from the server.

When any state change such as the occurrence of an error occurs in the server the server transmits part of the body indicating the state change to the HTTP client. Even when the transmission of the part of the body is completed the server does not transmit a notification of the completion of the transmission. Therefore both the HTTP client and the server maintain the state of being in the process of transmitting or receiving a body portion.

It is possible to implement status notification that is independent of the timing of the HTTP client by repeating the above noted process every time a state change of the server occurs.

In the end HTTP protocol compliant data formed of a header and a body result. This makes it possible to implement the status notification with software capable of performing common HTTP communications and in an environment where it is possible perform common HTTP communications.

When no response is returned from the server for a certain time the HTTP client may cut off communications. When no state change occurs in the server for a certain time the communications may be maintained by transmitting part of the body indicating the absence of a status change from the server.

According to HTTP it is possible to transmit various kinds of data such as text data image data XML data and JSON data. Recently data are more often transmitted and received in JSON format as use of Web services.

For the HTTP client there is a meaning in receiving individual partial data. Therefore it is easier for the HTTP client to perform processing when individual partial data are in a predetermined data format such as JSON format.

The HTTP client sequentially reads received data in accordance with the HTTP protocol. At this point a delimiter attached to the end of each data portion makes it possible to separately read individual partial data.

Referring to at step S the operation part application of the operation part which operates as an HTTP client transmits an HTTP request for status notification to the body part and the network management module receives the HTTP request. A session is established between the operation part application and the network management module by the HTTP request for status notification by the operation part application .

In response to the reception of the HTTP request at step S the network management module transmits a request for status notification to the Web service providing module .

The Web service providing module transmits a request for status notification to modules that manage statuses to be reported. Here at step S the Web service providing module transmits a request for status notification to the printer job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the copy job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the scanner job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the system management module .

Furthermore at step S the Web service providing module transmits an initial response that includes no status notification to the network management module .

In response at step S the network management module transmits a header only HTTP response to the operation part application . This HTTP response is not complete as a normal HTTP response so that the session remains maintained.

Thereafter at step S the operation part application transmits an HTTP request that specifies notification of Status A to the body part and the network management module receives the HTTP request.

In response to the reception of the HTTP request at step S the network management module transmits a request for status notification that specifies Status A to the Web service providing module .

The Web service providing module internally retains the specification of Status A and at step S returns a response to the network management module . At step S the network management module returns a response to the operation part application . The session of this request is completed by this.

Thereafter for example when the printer job management module detects a status change of Status A at step S the printer job management module transmits a response reporting the status change of Status A to the Web service providing module .

In response at step S the Web service providing module notifies the network management module of the status change of Status A as part of the response because the status change reported from the printer job management module matches the internally retained specification of Status A to be reported.

In response at step S the network management module transmits an HTTP response including the data of the status change of Status A as part of the body to the operation part application .

Thereafter when the system management module detects a status change of Status B at step S the system management module transmits a response reporting the status change of Status B to the Web service providing module .

In response the Web service providing module transmits no response because the status change reported from the system management module does not match the internally retained specification of Status A to be reported.

Thereafter if the operation part application transmits a request that specifies notification of Status B then notification is also performed with respect to a status change of Status B.

Like in the process illustrated in when there is no status change to report to the operation part application for a predetermined time the Web service providing module notifies the network management module of the absence of a status change as part of the response.

Furthermore the network management module transmits an HTTP response of the last part of the body to the operation part application at the time of for example turning off the body part the same as in the process of .

In the above described case the Web service providing module retains information on a status to be reported and determines whether to report a status change when being notified of the status change. Alternatively a status to be reported may be reported to a corresponding module and the module may determine whether to report a status change.

Referring to at step S the operation part application of the operation part which operates as an HTTP client transmits an HTTP request for status notification to the body part with respect to each function and the network management module receives the HTTP requests. A session is established between the operation part application and the network management module by the HTTP request for status notification by the operation part application with respect to each function.

In response to the reception of the HTTP requests at step S the network management module transmits a request for status notification to the Web service providing module with respect to each function.

The Web service providing module transmits a request for status notification to modules that manage statuses to be reported. Here at step S the Web service providing module transmits a request for status notification to the printer job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the copy job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the scanner job management module . Furthermore at step S the Web service providing module transmits a request for status notification to the system management module .

Furthermore at step S the Web service providing module transmits an initial response that includes no status notification to the network management module with respect to each function.

In response at step S the network management module transmits a header only HTTP response to the operation part application with respect to each function. This HTTP response is not complete as a normal HTTP response so that the session remains maintained with respect to each function.

Thereafter when the printer job management module detects a status change at step S the printer job management module transmits a response reporting the status change to the Web service providing module .

When the system management module detects a status change substantially at the same time with the detection of the status change by the printer job management module at step S the system management module transmits a response reporting the status change to the Web service providing module .

In response the Web service providing module notifies the network management module of the status change detected by the printer job management module as part of the response at step S and of the status change detected by the system management module as part of the response at step S.

In response the network management module transmits an HTTP response including the data of the status change detected by the printer job management module as part of the body to the operation part application at step S and transmits an HTTP response including the data of the status change detected by the system management module as part of the body to the operation part application at step S.

Thereafter when any of the printer job management module the copy job management module the scanner job management module and the system management module detects a status change an HTTP response including the data of the status change as part of the body is transmitted to the operation part application through the Web service providing module and the network management module .

Furthermore when there is no status change to report to the operation part application for a predetermined time the Web service providing module notifies the network management module of the absence of a status change as part of the response with respect to each request for status notification and the network management module transmits an HTTP response to the operation part application with respect to each request for status notification.

Furthermore when status notification becomes unnecessary the Web service providing module transmits a final response that completes the session to the network management module with respect to each request for status notification and the network management module transmits an HTTP response of the last part of the body to the operation part application with respect to each request for status notification so that the session is closed with respect to each function.

As described above according to the above described embodiment it is possible to ensure that changes in the status of an information processing apparatus operating as a server are reported in real time to an information processing apparatus operating as a client.

According to an aspect of the present invention an information processing apparatus of an information processing system using a protocol according to which a session with respect to a single request is completed by returning a predetermined response to the single request wherein another information processing apparatus transmits a request for status notification to the information processing apparatus and the information processing apparatus transmits a response of the status notification to the other information processing apparatus includes a processor and a memory storing instructions that when executed by the processor causes the information processing apparatus to transmit a header of the response of the status notification to the other information processing apparatus in response to receiving the request for the status notification from the other information processing apparatus transmit a part of a body of the response of the status notification to the other information processing apparatus in response to occurrence of a status change to be reported in the information apparatus the part of the body including information on the status change and transmit a last part of the body of the response of the status notification to the other information processing apparatus in response to the status notification becoming unnecessary.

According to an aspect of the present invention an information processing method executed by an information processing apparatus of an information processing system using a protocol according to which a session with respect to a single request is completed by returning a predetermined response to the single request wherein another information processing apparatus transmits a request for status notification to the information processing apparatus and the information processing apparatus transmits a response of the status notification to the other information processing apparatus includes transmitting a header of the response of the status notification to the other information processing apparatus in response to receiving the request for the status notification from the other information processing apparatus transmitting a part of a body of the response of the status notification to the other information processing apparatus in response to occurrence of a status change to be reported in the information apparatus the part of the body including information on the status change and transmitting a last part of the body of the response of the status notification to the other information processing apparatus in response to the status notification becoming unnecessary.

All examples and conditional language provided herein are intended for pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed as limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority or inferiority of the invention. An information processing system apparatus and method have been described based on one or more embodiments of the present invention. It should be understood however that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

