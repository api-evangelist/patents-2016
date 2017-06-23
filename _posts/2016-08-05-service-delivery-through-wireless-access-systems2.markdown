---

title: Service delivery through wireless access systems
abstract: A communication terminal comprising: a radio interface and a WLAN communication module configured to: generate and send an association request; receive an association response; and establish IP connectivity. The communication terminal also comprises a service selection module configured to select a computer-implemented service to be accessed; and a service execution control module configured to execute software application code implementing the selected computer-implemented service. The WLAN communication module is further configured to: in response to receiving a service selection command from the service selection module, generate an association request comprising a service identifier which identifies the selected service; parse the association response received through the radio interface to detect a link carried in the association response, wherein the link points to a network address of an application server suitable for delivering application data corresponding to the selected computer-implemented service; and initiate data communication with the network address for downloading application data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09614919&OS=09614919&RS=09614919
owner: ALE INTERNATIONAL
number: 09614919
owner_city: Colombes
owner_country: FR
publication_date: 20160805
---
This United States Patent Application is a continuation of International Patent Application PCT IB2016 050754 filed on Feb. 12 2016 which claims priority from European Patent Application Serial No. 16305072.7 filed on Jan. 26 2016 the entire content of which are incorporated herein by reference.

The invention relates to the technical field of service delivery through wireless access systems and infrastructures in particular in accordance with the IEEE 802.11 specification also known as Wi Fi.

Wi Fi is the dominant technology for Wireless Local Area Networks WLAN . A wireless communication terminal having an active Internet connection established through a WLAN can generally access all services that the Internet is able to provide. Service as employed herein refers to any computer implemented service e.g. information service entertainment service booking service reporting service monitoring service payment service authentication service communication service and others.

In addition to an active Internet connection accessing such services generally requires some kind of prior configuration of the communication terminal e.g. installing a software application that includes some embedded network addresses for communicating with predefined distant servers or inputting a URL in a web browser application.

The providing of services through Wi Fi communication terminals without the need to have an active Internet connection has also been proposed in the art in some rare cases. The publication 802.11 V. GUPTA et al. in International Journal of Computer Applications Vol. 63 No 2 February 2013 discloses a location specific advertisement service that relies on advertisements coupons discounts and commercial announcements being overloaded in beacon frames of a WLAN access point and therefore broadcasted in the coverage area of the access point. Such advertisement service is inherently limited in purpose and usability.

Aspects of the invention are based on the idea of offering a broad selection of computer implemented services through a wireless communication terminal lacking an active Internet connection. Aspects of the invention are based on the idea of offering computer implemented services through a wireless communication terminal in a way that limits the amount of prior configuration needed at the wireless communication terminal.

Aspects of the invention stem for the observation that situations exist in which it would be desirable to be able to launch a software application on a wireless communication terminal even though the software application is not yet installed and no network connection is yet available.

A local Wi Fi network is deployed in a hospital and publicly accessible for visitors wireless communication terminals to connect to the Internet or to a private network. The hospital administration develops a map assistance software application or web service to help visitors find their way in the buildings and facilities. A conventional method for accessing such software application or web service consists in firstly connecting the wireless communication terminal to the Wi Fi network secondly scanning a QR code which redirects the web browser application running on the wireless communication terminal towards the hospital web servers or towards a web portal from which the application may be downloaded and thirdly installing and launching the application on the wireless communication terminal. However it is observed that the user experience would be improved by enabling the user to learn about and select this map assistance service prior to connecting to the Wi Fi network and to have it launched as soon as the network connectivity is established.

A local Wi Fi network is deployed in an airport and publicly accessible for passengers wireless communication terminals to connect to the Internet or to a private network. Several software applications related to the airport context are made available through this Wi Fi network application for getting the flights time schedule application for checking the arrivals for finding one s way for booking a taxi etc. Instead of downloading all these applications once connected to the Wi Fi network it would be desirable for an end user to be able to select one of these applications prior to establishing the Wi Fi connection and to have it launched as soon as the connection is established.

Accordingly the invention is based on the idea of enabling an end user to select an application layer service i.e. OSI Layer 7 directly from the medium connection layer OSI network Layer 2 . In embodiments the invention enables to select an application that is not yet installed on a communication terminal prior to any network connection and to automatically launch the application with minimal further actions.

A data repository storing a directory of available services consisting of a set of service records wherein each service record comprises a service identifier and a network address of an application server suitable for delivering application data corresponding to a computer implemented service A control module configured to Parse an association request received through the radio interface to detect a service identifier carried in the association request Look up the directory of available services for retrieving a service record matching the detected service identifier Generate and send an association response to a source of the association request through the radio interface wherein the association response comprises a link to the network address found in the matching service record and Provide network connectivity between the source of the association request and the application server associated to the network address.

According to embodiments such a wireless access system can comprise one or more of the features below.

In embodiments each service record further comprises a service descriptor for describing the service to an end user and wherein the control module is further configured to 

broadcast beacon signals through the radio interface wherein the beacon signals include a service advertisement for a or each service record of the directory of available services wherein the service advertisement comprises the service identifier and the service descriptor found in the service record.

In embodiments the radio interface is configured to send and receive radio signals in accordance with an IEEE 802.11 specification wherein the association request association response and beacon signals are configured in accordance with the IEEE 802.11 specification.

In embodiments the beacon signal includes the service advertisement in a Vendor Specific field of the beacon signal.

In embodiments the or each service record further comprises at least one of a traffic requirement of the computer implemented service a Quality of Service QoS requirement of the computer implemented service an operating system OS requirement of the computer implemented service a version number of the computer implemented service a security level of the computer implemented service and a price of the computer implemented service. In embodiments the or each service advertisement further comprises at least one of the traffic requirement Quality of Service requirement operating system requirement version number security level and price found in the service record.

filter out a subsequent data packet received through the radio interface and intended to the network address of the application server in response to detecting that the data packet does not originate from the recorded source IP address and source MAC address.

In embodiments the link to the network address found in the matching service record points to a local address in the wireless access system wherein the control module is further configured to operate as a reverse proxy between the application server and the source of the association request.

In embodiments the application data comprises software application code encoding a web application executable by a web browser. In embodiments the application data comprises software application code encoding a software application executable by a processor of the communication terminal under the control of an operating system.

a service execution control module configured to execute software application code implementing the selected computer implemented service 

in response to receiving a service selection command from the service selection module generate an association request comprising a service identifier which identifies the selected service and

parse the association response received through the radio interface to detect a link carried in the association response wherein the link points to a network address of an application server suitable for delivering application data corresponding to the selected computer implemented service and

In an embodiment the WLAN communication module is further configured to parse beacon signals received through the radio interface to detect a service advertisement carried in the beacon signals indicative of a service available for selection and to communicate the service advertisement to the service selection module.

In an embodiment the service selection module is further configured for generating a graphical user interface for displaying a set of computer implemented services available for selection.

In an embodiment the graphical user interface displays a text descriptor for each computer implemented service available for selection.

In an embodiment the service selection module is further configured to filter the services available for selection as a function of information carried in the service advertisements and to generate the graphical user interface so as to display the filtered set of computer implemented services available for selection.

In an embodiment the information carried in the service advertisements comprises at least one of a traffic requirement of the computer implemented service a Quality of Service QoS requirement of the computer implemented service an operating system requirement of the computer implemented service a version number of the computer implemented service a security level of the computer implemented service and a price of the computer implemented service.

In the following the terms service and application refer to all kinds of tasks based on data processing in a computer environment and providing useful results to an end user such as an information service e.g. phone directory bus schedule an entertainment service e.g. gaming a booking service a reporting service a monitoring service a payment service an authentication service a communication service and others.

A service or application is implemented by means of application data which may include software code in source format or executable format written in any computer language e.g. HTML C JAVA VHDL Python ActiveX etc. Such application data may include functional data e.g. computer programs configuration files and functional parameters and cognitive data e.g. images text maps videos useful for implementing the service.

The WLAN infrastructures application servers and management stations are interconnected through any combination of wired or wireless IP networks that may include the Internet a wide area network a mobile telephone network an Ethernet LAN etc.

The communication terminal may include but is not limited to an electronic device in the form of a mobile telephone a combination personal digital assistant PDA and mobile phone an integrated messaging device a desktop computer a netbook computer a tablet computer etc. The same general description applies to management station .

Communication terminal may communicate using various transmission technologies including but not limited to Code Division Multiple Access CDMA Global System for Mobile Communications GSM Universal Mobile Telecommunications System UMTS Time Division Multiple Access TDMA Frequency Division Multiple Access FDMA Transmission Control Protocol Internet Protocol TCP IP Short Messaging Service SMS Multimedia Messaging Service MMS e mail Instant Messaging Service IMS Bluetooth IEEE 802.11 Worldwide Interoperability for Microwave Access WiMax LTE etc. A communication terminal involved in implementing various embodiments of the present invention may communicate using various media including but not limited to radio infrared laser cable connection and the like.

A WLAN infrastructure consists of at least one wireless Access Points AP i.e. APs and in the exemplary embodiment illustrated in and a data storage device for storing a directory of services available in the WLAN infrastructure i.e. directories and in the exemplary embodiment illustrated in . In a non illustrated embodiment a WLAN infrastructure comprises a plurality of APs interconnected through an aggregation network e.g. Ethernet LAN. The data storage device may be provided in an AP or as a separate device connected to the AP and may include any kind of computer readable medium e.g. removable or non removable such as a hard drive Read only memory ROM Random access memory RAM optical disc etc.

The operations of the communication system illustrated in will be best understood with the following illustrative use case.

We assume that there are two separate WLAN infrastructures and advertising different applications in a same geographical area e. g. a building such as a railway station. More precisely WLAN infrastructure advertises two applications identified by their respective identifiers app Id and app Id and short descriptions. Similarly WLAN infrastructure advertises two applications identified by their respective identifiers app Id and app Id and short descriptions.

The description of the application app Id may be Get the train arrivals time in the railway station . The description of the application app Id may be Call for free within railway station area .

In addition each WLAN infrastructure broadcasts an identifier so that it can be identified by communication terminals e.g. the Extended Service Set Identification ESSID according to IEEE 802.11 specifications. More precisely WLAN infrastructure advertises WiFi and WLAN infrastructure advertises WiFi as the ESSID.

In this context the following scenario can be implemented. A user in possession of communication terminal e.g. a mobile phone is located in a railway station and wants to get the train arrival times in this station. This railway station hosts two WLAN infrastructures and . When under the coverage of WLAN infrastructures and the communication terminal will detect and notify the user that applications app Id app Id and app Id are available for use with their corresponding descriptions such as for instance Get the train arrival times in the railway station for app Id. The communication terminal will provide a selection interface for the end user to select the desired application and desired WLAN infrastructure i.e. application app id in the present case and e.g. WiFi. Then the communication terminal starts the association procedure with WLAN infrastructure and gets the information from WLAN infrastructure that the application app Id is a web application available at a certain URL e.g. https trains.citystation.eu arrivals . Once connected to WLAN infrastructure the WLAN communication module of communication terminal requests the mobile operating system OS to launch the embedded web browser and navigate to the URL received during the association procedure. Since the communication terminal already indicated that it wanted to use the application app Id at the time of requesting association to the WLAN infrastructure the WLAN infrastructure when receiving the web request from the communication terminal will grant access to the corresponding resource by reverse proxy ing the web request towards the web server mapped to the above mentioned URL.

This scenario is depicted in more details in the flow charts of . These flow charts will be described in four main sequences of method steps.

A publishing API is offered by each WLAN infrastructure and . This API is used by application editors to publish and register their applications onto the WLAN infrastructure e.g. from the management station into the service directories and in the exemplary embodiment illustrated in . The publishing API may also be manually accessed by a network administrator configuring the WLAN infrastructure with a network configuration tool. The publishing API allows the editor to specify at least a short description of the application to be registered and a network address or Uniform Resource Locator URL from which the application code may be obtained. A unique identifier of the application must also be specified at the time of generating the service record in the directory of available services. Such identifier may be generated manually by the editor or automatically by the WLAN infrastructure.

In further embodiments the service record may include further characteristics. For example the publishing API enables to describe the application with the following parameters or some of them 

Within a WLAN infrastructure the or each AP retrieves the content of the directory of services and employs an extended beacon signal to broadcast a service advertisement for each application made available in the WLAN infrastructure. The service advertisement broadcasted comprises at least a unique identifier of each application and a plain text description to give useful information for the end user willing to select the most adequate application.

The service advertisements relating to applications made available in the WLAN infrastructure may be broadcasted using any suitable channel. The service advertisements may be carried in beacon frames or probe response frames. In an IEEE 802.11 compliant infrastructure i.e. WiFi the beacon frames include a Vendor Specific field which may be employed for carrying the service advertisements.

Service advertisements may comprise further information about the application. The information structure of the service advertisements in WLAN infrastructure may be represented by the JavaScript Object Notation JSON format depicted in Appendix 1.

When present in the shared coverage area of WLAN infrastructures and the communication terminal will receive the service advertisements from both infrastructures even before any network connection is established at IP layer. The communication terminal extracts the service advertisements from the beacon frames and provides a service selection interface adapted for the end user to learn about the available applications and select one or more of them that the end user intends to launch.

The service selection interface can be a graphical user interface GUI text based user interface voice user interface mixed mode interface and the like. Functionality expressed within the service selection interface can be present within file menus context menus menu bars toolbars audio description and the like. The service selection interface can include one or more graphical user interface elements including but not limited to checkboxes radio dialogs combo boxes and the like. The service selection interface can receive input and or selection via traditional and or proprietary mechanisms including keyboard mouse gesture voice and the like.

An illustrative GUI generated by communication terminal receiving service advertisements and is a window showing this 

Namely the communication terminal displays to the end user a list of available WiFi networks and a list of available applications in each WiFi network.

In an embodiment the service selection module can filter the services available for selection as a function of information carried in the service advertisements. For example the service selection module can restrict the list of available applications as a function of the Type to offer only those supported by the OS platform of communication terminal .

Functionality for launching the selected application is shared between the WLAN infrastructure and the communication terminal .

The WLAN association mechanism employed enables the WLAN client to specify to the WLAN infrastructure which application the end user wants to launch after obtaining network connectivity. The WLAN infrastructure will also use this association mechanism to provide the WLAN client some information necessary to launch the application. As part of the Application launching step the WLAN infrastructure may also provide some authentication and authorization procedures to grant access to the application depending on the user.

IEEE 802.11 standards require any WLAN client to associate to an AP prior to obtaining IP connectivity with the network. The association step enables to exchange WLAN connection capability and get access to the WLAN infrastructure. Messages employed in such association step can serve to carry additional parameters e.g. in a vendor specific part of the WiFi messages or in dedicated fields in order to trigger processes relating to the desired application at the same time e.g. downloading and execution.

Upon receiving Association Response message communication terminal associates to the WLAN AP and extracts the URL of the web server. Since the selected application is tagged as a Web Application communication terminal also launches a web browser targeting this URL as the open web page or web resource.

When the WLAN infrastructure receives an HTTP request corresponding to this URL it may perform some authentication method to check if the client originating the request namely communication device is allowed to access the web page. In an embodiment AP compares an identifier of the client originating the HTTP request e.g. MAC Address IP address of client to previously cached identifiers representing the clients associated to the WLAN infrastructure and which indicated that they wanted to access the selected application i.e. App id. Such comparison makes it possible to deny access when the request comes from a source address that was not previously known i.e. cached or registered.

If authentication is successful or disabled the WLAN infrastructure will forward the request to the Web Page. In an embodiment the URL given in the Association Response message is a local address valid only in the WLAN infrastructure and associated to a public address e.g. FQDN of the web server registered in the service directory. In other words the WLAN infrastructure can operate as a Web proxy.

The above described operations for launching the application are slightly modified in the case of a software application that requires some prior configuration steps prior to execution i.e. downloading and installation. In such case after the communication terminal gets the URL to the application server during the association step it silently starts downloading the software application code from the application server from an application store or directly from the WLAN infrastructure which could act as a mirror. Then WLAN control module will request the OS module to install and launch the software application.

The methods described hereinabove may be executed through the use of dedicated hardware as well as hardware capable of executing software in association with appropriate software. When provided by a processor the corresponding functions may be provided by a single dedicated processor by a single shared processor or by a plurality of individual processors some of which may be shared. Moreover explicit use of the term processor or controller should not be construed to refer exclusively to hardware capable of executing software and may implicitly include without limitation digital signal processor DSP hardware network processor application specific integrated circuit ASIC field programmable gate array FPGA read only memory ROM for storing software random access memory RAM and non volatile storage. Other hardware conventional and or custom may also be included.

The invention is not limited to the described embodiments. The appended claims are to be construed as embodying all modification and alternative constructions that may be occurred to one skilled in the art which fairly fall within the basic teaching here set forth.

The use of the verb to comprise or to include and its conjugations does not exclude the presence of elements or steps other than those stated in a claim. Furthermore the use of the article a or an preceding an element or step does not exclude the presence of a plurality of such elements or steps.

In the claims any reference signs placed between parentheses shall not be construed as limiting the scope of the claims.

