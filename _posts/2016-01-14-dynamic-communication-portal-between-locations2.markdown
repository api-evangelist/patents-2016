---

title: Dynamic communication portal between locations
abstract: Technology is disclosed herein that enhances communication and collaboration at a distance. In an implementation, a portal engine provides a communication and content portal through which users situated in different locations may interact and collaborate with each other. The portal includes an always-on, bi-directional video link through which the users may communicate over video. The portal may also include a digital white-board or other surface link over which shared content may be exchanged.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09628757&OS=09628757&RS=09628757
owner: Microsoft Technology Licensing, LLC
number: 09628757
owner_city: Redmond
owner_country: US
publication_date: 20160114
---
This application is related to claims priority to and incorporates by reference in its entirety U.S. Provisional Patent Application No. 62 205 637 entitled Dynamic Communication Portal Between Locations and filed on Aug. 14 2015.

A wide variety of communication tools exist to allow people to communicate and collaborate at a distance from each other. Traditional phone conferencing systems video conferencing systems and other similar technologies are just some examples. Collaboration tools also allow users to collaborate on work such as to edit shared documents and the like.

Such solutions typically require a good amount of coordination beforehand and are usually limited to people participating via their personal computing system such as a desktop laptop or tablet computer mobile phone or other similar devices. The overall effect is relatively impersonal and lacks any of the spontaneity that might be encountered in a live in person situation. From a more technical perspective all of this requires a great deal of effort coordination and equipment on the part of each user.

Lately it has become popular to establish an always on video link between two locations to allow people to interact with each other in a more spontaneous less structured way. Sometimes this is accomplished in a relatively simple way by two people leaving a video call on at their desks for example. But even this approach presents drawbacks from a technical perspective such as the lack of security and privacy as well as the resources wasted between the two locations when the two people are not communicating.

Technology is disclosed herein that enhances communication and collaboration at a distance. In an implementation a portal engine provides a communication and content portal through which users situated in different locations may interact and collaborate with each other. The portal includes an always on bi directional video link through which the users may communicate over audio and video. The portal also includes a digital white board or surface link over which shared content may be exchanged.

In a specific implementation the video link renders a reduced quality or dormant view of each location until the link is activated by a user on either end at which time video from that end transitions to a high quality image. The always on nature of the link allows users from one location to see goings on at the other location in rough detail until a person at the location activates their end of the portal at which time the video transitions to finer grained detail. Such an arrangement provides a technical effect of always on video while preserving privacy and security to a certain extent.

This Overview is provided to introduce a selection of concepts in a simplified form that are further described below in the Technical Disclosure. It may be understood that this Overview is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

Other elements may be included in operational environment in addition to portal engine such as video capture equipment motion analyzer equipment facial recognition equipment surface computing equipment and the like. Portal engine may be integrated within any other element distributed across multiple elements or implemented as a stand alone system.

In operation the exchange of portal content is facilitated by portal engine . Referring parenthetically to the steps illustrated in the following describes at last some of the functionality provided by portal engine when executing process .

Portal engine maintains an always on bi directional video link between at least two locations represented in by the local scene and the remote scene step . User is situated in the local scene while user and user are situated in the remote scene. The users may engage with a surface e.g. a digital white board facilitated by a white board link maintained by portal engine step .

The users may interact with their local environment including speaking gesturing motioning or otherwise engaging with video link . Likewise the users may interact with the digital white board such as by writing on it touching it gesturing towards it holding or placing objects in proximity to it or in any other manner. Such user input is represented by user interaction and user interaction .

Portal engine analyzes the user interactions and as they occur to determine whether or not or how to modify the presentation of portal content step . When user engages with the portal for example a remote presentation of the portal experience may be modified by portal engine accordingly step .

For instance user may engage with the video link in such a way that portal engine transitions the link from a cold state less detailed obscured to a hot state full detail un obscured . In another example a user may write on the digital white board. The content may be captured and displayed on that user s white board but also replicated on a corresponding white board at the remote location.

Relationship recognition between shapes and other objects on the white board by portal engine is also possible. As objects are manipulated by a user dragging them around for instance their visual relationships may remain intact while the manipulation is replicated on the far end of the portal.

Yet another example of the capability of portal engine is the ability to recognize ordered lists of written tasks or other items. Each string can be recognized as its own self contained object allowing it to be manipulated like a shape. However an overall structure of the list is also recognized such that as one string is manipulated it has an impact on the positioning and layout of other strings around it.

Portal engine is further capable of recognizing physical objects that are presented to a surface and rendering a virtual representation of the objects on the surface. For instance a user might place a design sample paint swab carpet sample against the surface to be recognized and rendered virtually by portal engine . This allows participants on the far end to interact with physical objects possessed by participants on the near end.

Computing device is also included in operational scenario . Computing device also includes a canvas and a video portal . Thus content may be shared between user situated in a local scene and users and situated remotely from user . In addition video portal and video portal may be coupled by an always on bi directional video link.

In video portal and video portal are both in a dormant state. The video link between them is on but the video of each respective scene is configured such that the opposing scene is obscured somewhat. For example the video in video portal shows a faint outline of two users user and user while the video in video portal shows a faint outline of user . Alternatively or additionally any audio associated with the video may be suppressed in the dormant state.

In user interacts with video portal represented by interaction . User may for example touch the surface speak a command make a particular gesture or otherwise indicate an intent to communicate through the portal.

In response to the interaction one or both of video portal and video portal transitions from a cold state to a hot state. In one embodiment as the interaction indicates that a person in the remote scene wishes to communicate with anyone at the far end of the portal video portal may transition first to the hot scene. Assuming user reciprocates then video portal would also transition from the cold to hot state.

Indeed illustrates both portals in their hot state. That is the video rendered in both portals is no longer obscured in any manner and he associated audio is activated allowing for full communication and interaction between participants at either end of the portal.

The portal engine also recognizes the relationships implied by the connections drawn between each circular shape. A is connected to B and C B is connected to A and C and C is connected to B and A. Thus when C is moved by a user interaction with the canvas in the relationships are maintained between the shapes. The manipulation is also reflected in the version rendered on canvas .

The list has an order implied by the order in which the elements were written on the canvas. In addition the list has a comprehensive structure that is recognized by the portal engine. This allows elements within the list to be manipulated by users and re ordered by dragging and dropping the elements. illustrates an example whereby a manipulation moves the third element in the list install pump to the second place in the list. The manipulation is detected by the portal engine and the third element replaces the second. As shown in the second element is automatically pushed down in the list even though the manipulation does not involve the second element. The re ordering of the list is also reflected on canvas .

In a virtual representation of the object is rendered on canvas . In addition the virtual representation is rendered on canvas . This allows users and to share physical objects with user located remotely from them. User can inspect the virtual representation of the object for example.

In a user approaches the portal at the far end and triggers its transition at the near end to a hot state. The portal begins to expand horizontally and the video is clarified. In the video portal has transitioned fully to a hot state.

Still referring to the portal technology disclosed herein allows local and remote teams to bridge the geographic divide and collaborate in person in both a planned and an ad hoc manner. Sometimes referred to as a warm portal because it is an always on connection to a remote location that changes state depending on the engagement of team members the warm portal can be on any touch surface or non touch surface with a camera and audio capabilities.

People in either location can engage with the portal by touching the touch surface or programmatically using recognition on a non touch surface. When at rest the warm portal appears as a narrow black and white hazed vertical strip in some implementations.

Because it is always on one can see movement as people cross in and out of the viewing area however the hazing of the view doesn t show crisp detail for privacy bandwidth and or other purposes . When engaged the warm portal goes hot flooding to twice its at rest width and becoming in focus and full color where possible.

Remote participants can engage with local team members naturally and at a comfortable conversational angle. When participants disengage the warm portal returns to its at rest state

Computing system may be implemented as a single apparatus system or device or may be implemented in a distributed manner as multiple apparatuses systems or devices. Computing system includes but is not limited to processing system storage system software communication interface system and user interface system . Processing system is operatively coupled with storage system communication interface system and user interface system .

Processing system loads and executes software from storage system . Software includes process which is representative of the processes discussed with respect to the preceding including process . When executed by processing system software directs processing system to operate as described herein for at least the various processes operational scenarios and sequences discussed in the foregoing implementations. Computing system may optionally include additional devices features or functionality not discussed for purposes of brevity.

Referring still to processing system may comprise a micro processor and other circuitry that retrieves and executes software from storage system . Processing system may be implemented within a single processing device but may also be distributed across multiple processing devices or sub systems that cooperate in executing program instructions. Examples of processing system include general purpose central processing units application specific processors and logic devices as well as any other type of processing device combinations or variations thereof.

Storage system may comprise any computer readable storage media readable by processing system and capable of storing software . Storage system may include volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Examples of storage media include random access memory read only memory magnetic disks optical disks flash memory virtual memory and non virtual memory magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other suitable storage media. In no case is the computer readable storage media a propagated signal.

In addition to computer readable storage media in some implementations storage system may also include computer readable communication media over which at least some of software may be communicated internally or externally. Storage system may be implemented as a single storage device but may also be implemented across multiple storage devices or sub systems co located or distributed relative to each other. Storage system may comprise additional elements such as a controller capable of communicating with processing system or possibly other systems.

Software may be implemented in program instructions and among other functions may when executed by processing system direct processing system to operate as described with respect to the various operational scenarios sequences and processes illustrated herein. For example software may include program instructions for implementing enhanced portal communication and collaboration.

In particular the program instructions may include various components or modules that cooperate or otherwise interact to carry out the various processes and operational scenarios described herein. The various components or modules may be embodied in compiled or interpreted instructions or in some other variation or combination of instructions. The various components or modules may be executed in a synchronous or asynchronous manner serially or in parallel in a single threaded environment or multi threaded or in accordance with any other suitable execution paradigm variation or combination thereof. Software may include additional processes programs or components such as operating system software virtual machine software or other application software in addition to or that include process . Software may also comprise firmware or some other form of machine readable processing instructions executable by processing system .

In general software may when loaded into processing system and executed transform a suitable apparatus system or device of which computing system is representative overall from a general purpose computing system into a special purpose computing system customized to facilitate enhanced communication and collaboration. Indeed encoding software on storage system may transform the physical structure of storage system . The specific transformation of the physical structure may depend on various factors in different implementations of this description. Examples of such factors may include but are not limited to the technology used to implement the storage media of storage system and whether the computer storage media are characterized as primary or secondary storage as well as other factors.

For example if the computer readable storage media are implemented as semiconductor based memory software may transform the physical state of the semiconductor memory when the program instructions are encoded therein such as by transforming the state of transistors capacitors or other discrete circuit elements constituting the semiconductor memory. A similar transformation may occur with respect to magnetic or optical media. Other transformations of physical media are possible without departing from the scope of the present description with the foregoing examples provided only to facilitate the present discussion.

Communication interface system may include communication connections and devices that allow for communication with other computing systems not shown over communication networks not shown . Examples of connections and devices that together allow for inter system communication may include network interface cards antennas power amplifiers RF circuitry transceivers and other communication circuitry. The connections and devices may communicate over communication media to exchange communications with other computing systems or networks of systems such as metal glass air or any other suitable communication media. The aforementioned media connections and devices are well known and need not be discussed at length here.

User interface system is optional and may include a keyboard a mouse a voice input device a touch input device for receiving a touch gesture from a user a motion input device for detecting non touch gestures and other motions by a user and other comparable input devices and associated processing elements capable of receiving user input from a user. Output devices such as a display speakers haptic devices and other types of output devices may also be included in user interface system . In some cases the input and output devices may be combined in a single device such as a display capable of displaying images and receiving touch gestures. The aforementioned user input and output devices are well known in the art and need not be discussed at length here.

User interface system may also include associated user interface software executable by processing system in support of the various user input and output devices discussed above. Separately or in conjunction with each other and other hardware and software elements the user interface software and user interface devices may support a graphical user interface a natural user interface or any other type of user interface.

Communication between computing system and other computing systems not shown may occur over a communication network or networks and in accordance with various communication protocols combinations of protocols or variations thereof. Examples include intranets internets the Internet local area networks wide area networks wireless networks wired networks virtual networks software defined networks data center buses computing backplanes or any other type of network combination of network or variation thereof. The aforementioned communication networks and protocols are well known and need not be discussed at length here. However some communication protocols that may be used include but are not limited to the Internet protocol IP IPv4 IPv6 etc. the transfer control protocol TCP and the user datagram protocol UDP as well as any other suitable communication protocol variation or combination thereof.

In any of the aforementioned examples in which data content or any other type of information is exchanged the exchange of information may occur in accordance with any of a variety of protocols including FTP file transfer protocol HTTP hypertext transfer protocol REST representational state transfer WebSocket DOM Document Object Model HTML hypertext markup language CSS cascading style sheets HTML5 XML extensible markup language JavaScript JSON JavaScript Object Notation and AJAX Asynchronous JavaScript and XML as well as any other suitable protocol variation or combination thereof.

Certain inventive aspects may be appreciated from the foregoing disclosure of which the following are various examples.

A computing apparatus comprising one or more computer readable storage media a processing system operatively coupled with the one or more computer readable storage media and program instructions stored on the one or more computer readable storage media that when read and executed by the processing system direct the processing system to at least maintain a bi directional video link between a plurality of locations comprising video captured of each of the plurality of locations present a dormant view of each location captured in the video on a display surface at each other location until the video link is activated by user interaction with the display surface at any one of the plurality of locations and when the video link is activated by the user interaction transition the dormant view to an active view of at least the location where the user interaction occurred.

The computing system of Example 1 wherein the dormant view has a reduced quality relative to a higher quality of the active view.

The computing system of Examples 1 2 the reduced quality comprises an out of focus effect and wherein the higher quality comprises an in focus effect.

The computing system of Examples 1 3 wherein the reduced quality further comprises a reduced width of the video and wherein the higher quality comprises an expanded width.

The computing system of Examples 1 4 wherein the reduced quality further comprises a limited color effect and wherein the higher quality comprises a full color effect.

The computing system of Examples 1 5 wherein the reduced quality further comprises a reduced width of the video and wherein the higher quality comprises an expanded width.

The computing system of Examples 1 6 wherein the user interaction comprises a touch on the display surface to initiate the transition from the dormant view to the active view.

The computing system of Examples 1 7 wherein the program instructions further direct the processing system to present a shared digital whiteboard adjacent to the video on the display surface at each of the plurality of locations.

A method of operating a bi directional video link maintained between a plurality of locations the method comprising capturing video of each of the plurality of locations presenting a dormant view of each location captured in the video on a display surface at each other location until the video link is activated by user interaction with the display surface at any one of the plurality of locations and when the video link is activated by the user interaction transitioning the dormant view to an active view of at least the location where the user interaction occurred.

The method of Example 9 wherein the dormant view has a reduced quality relative to a higher quality of the active view.

The method of Examples 9 10 wherein the reduced quality comprises an out of focus effect and wherein the higher quality comprises an in focus effect.

The method of Examples 9 11 wherein the reduced quality further comprises a limited color effect and wherein the higher quality comprises a full color effect.

The method of Examples 9 12 wherein the reduced quality further comprises a reduced width of the video and wherein the higher quality comprises an expanded width.

The method of Examples 9 13 wherein the user interaction comprises a touch on the display surface to initiate the transition from the dormant view to the active view.

The method of Examples 9 14 further comprising presenting a shared digital whiteboard adjacent to the video on the display surface at each of the plurality of locations.

A method of operating an online portal between at least two locations comprising maintaining an always on bi directional video link between a plurality of locations maintaining a content link between the plurality of locations analyzing user interaction at each of the plurality of locations modifying a remote presentation of content at each other of the plurality of locations to reflect the user interaction at any one of the plurality of locations.

The method of Example 16 further comprising capturing video of each of the plurality of locations presenting a dormant view of each location captured in the video on a display surface at each other location until the video link is activated by additional user interaction with the display surface at any one of the plurality of locations and when the video link is activated by the additional user interaction transitioning the dormant view to an active view of at least the location where the user interaction occurred.

The method of Examples 16 17 further comprising presenting a shared whiteboard adjacent to the video on the display surface at each of the plurality of locations and rendering the remote presentation of the content on the shared whiteboard space at each of the plurality of locations.

The method of Examples 16 18 further comprising recognizing a physical object that is presented to the display surface and rendering a virtual representation of the object on the display surface.

The method of Examples 16 19 wherein the user interaction comprises a touch interaction with the virtual representation of the object.

The functional block diagrams operational scenarios and sequences and flow diagrams provided in the Figures are representative of exemplary systems environments and methodologies for performing novel aspects of the disclosure. While for purposes of simplicity of explanation methods included herein may be in the form of a functional diagram operational scenario or sequence or flow diagram and may be described as a series of acts it is to be understood and appreciated that the methods are not limited by the order of acts as some acts may in accordance therewith occur in a different order and or concurrently with other acts from that shown and described herein. For example those skilled in the art will understand and appreciate that a method could alternatively be represented as a series of interrelated states or events such as in a state diagram. Moreover not all acts illustrated in a methodology may be required for a novel implementation.

The descriptions and figures included herein depict specific implementations to teach those skilled in the art how to make and use the best option. For the purpose of teaching inventive principles some conventional aspects have been simplified or omitted. Those skilled in the art will appreciate variations from these implementations that fall within the scope of the invention. Those skilled in the art will also appreciate that the features described above can be combined in various ways to form multiple implementations. As a result the invention is not limited to the specific implementations described above but only by the claims and their equivalents.

