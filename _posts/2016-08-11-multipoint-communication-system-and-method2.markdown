---

title: Multipoint communication system and method
abstract: A multipoint communication server for establishing multipoint communication between a plurality of endpoints, the multipoint communication server comprising: a data repository containing the set of endpoints identifiers wherein each endpoint identifier corresponds to a participating endpoint, a media processing unit configured to receive an upstream media stream from an emitting endpoint, the media processing unit being further configured to generate a plurality of downstream media streams for the participating endpoints, wherein the data repository further contains a replication inhibition set which consists of a subset of the set of endpoint identifiers and comprises at least the endpoint identifier of the emitting endpoint, wherein the media processing unit is configured to generate the downstream media stream for each participating endpoint whose endpoint identifier belongs to the replication inhibition set so that the downstream media stream does not replicate the upstream media stream.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09549154&OS=09549154&RS=09549154
owner: ALE INTERNATIONAL
number: 09549154
owner_city: Colombes
owner_country: FR
publication_date: 20160811
---
This United States Patent Application is a continuation of International Patent Application PCT IB2015 055586 filed on Jul. 23 2015 which claims priority from European Patent Application Serial No. 15306136.1 filed on Jul. 9 2015 the entire content of which are incorporated herein by reference.

The invention relates to multipoint communication systems and methods in particular for communicating video and or audio streams between a plurality of communication endpoints.

Along with the increase of bandwidth capabilities in communication systems audio and or video communication systems have become increasingly popular in both business and residential applications. Indeed in the case of geographically distributed team collaboration these systems avoid the travelling of the team collaborators and increase flexibility.

Audio or videoconferencing technologies use video and or audio communication to allow a plurality of people to communicate at a same time for instance for meeting activities. Furthermore besides the audio and or visual transmission of meeting activities videoconferencing technologies can be used to share documents and display information.

Each user participating to an audio and or videoconference is recorded and or filmed by a microphone and or a camera at an endpoint. The microphone and or camera generates an audio stream of the voice of the user and or a video stream representing the user in his her own environment.

An aspect of the invention is to provide audio conferencing systems and methods for echo cancellation between multiple participants located at earshot distance from one another.

In an embodiment the invention provides a multipoint communication server for establishing multipoint communication between a plurality of endpoints 

a session control interface configured to receive a set of endpoint identifiers wherein each endpoint identifier identifies a participating endpoint which participates to a multipoint communication session 

wherein the data repository further contains a replication inhibition set associated to the emitting endpoint wherein the replication inhibition set consists of a subset of the set of endpoint identifiers of the participating endpoints wherein the replication inhibition set comprises at least the endpoint identifier of the emitting endpoint 

wherein the media processing unit is configured to generate the downstream media stream for each participating endpoint whose endpoint identifier does not belong to the replication inhibition set so that the downstream media stream does replicate the upstream media stream.

Thanks to these features the multipoint communication server inhibits replicating a media stream coming from a participant to one or more other participants as defined in the replication inhibition set. This may be done for various purpose e.g. to avoid noise redundancy or distraction effects on the other participants.

According to embodiments such a multipoint communication server may comprise one or more of the features below.

In an embodiment the multipoint communication server may comprise a session control unit for controlling the multipoint communication session.

in response to determining that the third participating endpoint is a participating endpoint whose endpoint identifier belongs both to the first replication inhibition set and to the second replication inhibition set generate the downstream media stream for the third participating endpoint so that the downstream media stream replicates neither the first upstream media stream nor the second upstream media stream.

Alternatively this last test may be useless for example in the case wherein no participating endpoint is allowed to belong to two different replication inhibition sets.

The downstream media stream may be generated in a number of different manners for the third participating endpoint. When the media processing unit receives a plurality of upstream media streams from the participating endpoints of the multipoint communication session in an embodiment the downstream media stream for the third participating endpoint is generated by mixing each received upstream media stream excepting the upstream media streams incoming from participating endpoints whose endpoint identifiers belong to a same replication inhibition set as the third participating endpoint. In another embodiment the downstream media stream for the third participating endpoint is generated by mixing each received upstream media streams then by removing from the downstream media stream the upstream media streams incoming from participating endpoints whose endpoint identifiers belong to a same replication inhibition set as the third participating endpoint.

In an embodiment the third participating endpoint is associated to a replication inhibition set in the data repository.

In an embodiment the media processing unit is configured to further select received upstream media streams incoming from each participating endpoint whose power level is below a threshold to generate a second selection of upstream media streams and

to further generate the intermediate and global mixes by excluding the second selection of upstream media streams.

In an embodiment a replication inhibition set is associated to each communication endpoint whose endpoint identifier belongs to the replication inhibition set.

In an embodiment the media stream is selected in the set consisting of video stream audio stream data or file sharing streams.

The replication inhibition sets may be generated as a function of diverse criteria depending on specific applications. For example the replication inhibition set may be generated as a function of locations of the participants so as to take into account direct interactions between the participants that take place in the physical world outside the multipoint communication system. The replication inhibition sets may also be generated as a function of language preferences of the participants e.g. in a multilingual telephone conference.

In an embodiment the communication endpoints may directly inform the multipoint communication system from their locations based on Dual tone multi frequency signaling DTMF .

In an embodiment the invention also provides a localization system for establishing a replication inhibition set among a set of communication endpoints the localization system comprising a receiver and a data repository 

receive a first presence message from a first communication endpoint wherein the first presence message comprises a first endpoint identifier which identifies the first communication endpoint 

receive a second presence message from a second communication endpoint wherein the second presence message comprises a second endpoint identifier which identifies the second communication endpoint the localization system being configured to 

store the first endpoint identifier and the second endpoint identifier into a replication inhibition set into the data repository in response to determining that the first communication endpoint and the second communication endpoint are located in a mutual vision area or a mutual hearing area.

In an embodiment the first presence message further comprises a first position and the second presence message further comprises a second position wherein the localization system is further configured to determine that distance between the first and the second positions is lower than a threshold for determining that the first communication endpoint and the second communication endpoint are located in a mutual vision area or a mutual hearing area.

In an embodiment the localization system is further configured to determine a beacon identifier associated to the first conferencing endpoint as a function of the first message a beacon identifier associated to the second conferencing endpoint as a function of the second message and determine that beacon identifiers associated to the first and second conferencing endpoints are identical for determining that the first communication endpoint and the second communication endpoint are located in a mutual vision area or a mutual hearing area.

In an embodiment the first presence message further comprises a first beacon identifier and the second presence message further comprises a second beacon identifier wherein the localization system is further configured to determine that the first and second beacon identifiers are identical for determining that the first communication endpoint and the second communication endpoint are located in a mutual vision area or a mutual hearing area.

In an embodiment the localization system according further comprises a transmitter configured to send the replication inhibition set to a multipoint communication server.

In an embodiment the localization system is further configured to broadcast a request for presence report intended to cause the communication endpoint to send a presence message to the localization system. In an embodiment the request is sent periodically in order to allow a heartbeat mechanism.

In an embodiment the receiver is selected in the set consisting of a WiFi access point a Bluetooth access point a radio access point or any combination thereof.

In an embodiment an endpoint identifier is selected in the set consisting of a media access control MAC address a local identifier ID a network access ID a cell ID or any combination thereof.

In an embodiment the invention also provides a conferencing system comprising the multipoint communication server and the localization system hereinabove described.

In an embodiment the conferencing system further comprises the participating endpoints wherein the participating endpoints are configured to 

transmit upstream media streams to the multipoint communication server and receive downstream media streams from the multipoint communication server. In an embodiment at least one participating endpoints is further configured to send a presence message to the localization system in response to receiving the broadcasted request from the localization system.

In an embodiment the invention also provides a method for establishing multipoint communication between a plurality of endpoints the method comprising 

accessing a set of endpoint identifiers wherein each endpoint identifier identifies a participating endpoint which participates to a multipoint communication session 

controlling a multipoint communication session between a plurality of participating endpoints identified by a set of endpoint identifiers wherein each endpoint identifier corresponds to a participating endpoint 

receiving a second upstream media stream from a second emitting endpoint among the participating endpoints of the multipoint communication session wherein the data repository further contains a second replication inhibition set associated to the second emitting endpoint wherein the second replication inhibition set consists of a subset of the set of endpoint identifiers of the participating endpoints wherein the second replication inhibition set comprises at least the endpoint identifier of the second emitting endpoint 

in response to determining that a third participating endpoint is a participating endpoint whose endpoint identifier belongs neither to the first replication inhibition set nor to the second replication inhibition set mixing together the first and second upstream media streams incoming from the first and second emitting endpoints in order to generate the downstream media stream for the third participating endpoint and 

in response to determining that the third participating endpoint is a participating endpoint whose endpoint identifier belongs to the first replication inhibition set and not to the second replication inhibition set generating the downstream media stream for the third participating endpoint to replicate the second upstream media stream without replicating the first upstream media stream and

in response to determining that the third participating endpoint is a participating endpoint whose endpoint identifier belongs to the second replication inhibition set and not to the first replication inhibition set generating the downstream media stream for the third participating endpoint to replicate the first upstream media stream without replicating the second upstream media stream.

in response to determining that the third participating endpoint is a participating endpoint whose endpoint identifier belongs both to the first replication inhibition set and to the second replication inhibition set generating the downstream media stream for the third participating endpoint so that the downstream media stream replicates neither the first upstream media stream nor the second upstream media stream.

receiving a plurality of upstream media streams from the participating endpoints of the multipoint communication session 

selecting among the plurality of received upstream media streams each received upstream media stream incoming from a participating endpoint whose endpoint identifier belongs to the replication inhibition set in order to generate a selection of upstream media streams 

generating a global mix by mixing the intermediate mix with all other received upstream media streams among the plurality of received upstream media streams 

in response to determining that a third participating endpoint is a participating endpoint whose endpoint identifier does not belong to the replication inhibition set removing from the global mix at least the upstream media stream incoming from the third participating endpoint to generate a downstream media stream for the third participating endpoint 

in response to determining that the third participating endpoint is a participating endpoint whose endpoint identifier belongs to the replication inhibition set removing from the global mix the intermediate mix to generate a downstream media stream for the third participating endpoint.

In an embodiment the method further comprises selecting received upstream media streams incoming from each participating endpoint whose power level is below a threshold to generate a second selection of upstream media streams and

to further generate the intermediate and global mixes by excluding the second selection of upstream media streams.

receiving a plurality of upstream media streams encoded in Real Time Protocol packets from the plurality of participating endpoints 

converting each received upstream media stream in order to generate a respective numerical packet in a same linear format 

temporarily storing the respective numerical packets in association with the endpoint identifier of the respective participating endpoint from which the received upstream media stream originates 

linearly summing the numerical packets associated with endpoint identifiers belonging to the replication inhibition set in order to generate the intermediate mix 

linearly summing the other numerical packets with the intermediate mix in order to generate the global mix.

in response to determining that a third participating endpoint is a participating endpoint whose endpoint identifier does not belong to the replication inhibition set subtracting from the global mix the numerical packet associated to the endpoint identifier of the third participating endpoint in order to generate the downstream media stream for the third participating endpoint 

in response to determining that a third participating endpoint is a participating endpoint whose endpoint identifier belongs to the replication inhibition set subtract from the global mix the intermediate mix in order to generate the downstream media stream for the third participating endpoint 

In an embodiment a replication inhibition set is associated to each communication endpoint whose endpoint identifier belongs to the replication inhibition set.

In an embodiment the invention also provides a method for establishing a replication inhibition set among a set of communication endpoints the method comprising 

receiving a second presence message from a second communication endpoint wherein the second presence message comprises a second endpoint identifier which identifies the second communication endpoint 

storing the first endpoint identifier and the second endpoint identifier into a replication inhibition set into the data repository in response to determining that the first communication endpoint and the second communication endpoint are located in a mutual vision area or a mutual hearing area.

During a telephone conference all the participants to the conference and their respective user devices are not necessarily located in different geographical sites. When several participants are located in a same geographical site defined as a mutual hearing area i.e. are located at earshot distance from one another a first participant located near a second participant hears the second participant both directly and through the phone conference. Indeed the first participant hears directly the second participant speaking because of the proximity. Moreover when not avoided the first participant also hears the second participant indirectly through the user device of the first participant.

Similarly when several participants are located in a same geographical site defined as a mutual vision area i.e. when the participants are able to see each other without moving a first participant located near a second participant sees the second participant both directly and through a personal display screen which can cause distraction for the first participant. For example two colleagues participating to a same videoconference can sit around a table and have each a personal laptop.

Similarly two colleagues participating to a same videoconference can sit beside each other and the first colleague can share a document displayed on his personal laptop through the videoconference with a third participant located in a different geographical site. In this case the document is uselessly duplicated on the laptop of the second colleague which can both see the document on the laptop of the first colleague and on his personal laptop which can distract him. A conferencing endpoint is a user s device from which media streams are started and terminated during a conference. Each user device at each conferencing endpoint includes a microphone and or a capture device for instance a camera to capture an individual media stream from the user in his her environment. For example a conferencing endpoint may comprise a PC a laptop a tablet a deskphone a mobile phone a smartphone a conference specialized hardware and or any other device having a microphone and or a capture device and or a display device and or a loudspeaker. All the captured individual media streams should be processed to generate one or more media stream e.g. videoconference scenes and or voice stream which in turn must be sent to all other conferencing endpoints participating to the conference.

The invention provides a multipoint communication server configured to avoid undesirable echoes between participants located in a mutual hearing area or undesirable image redundancy between participants located in a mutual vision area. The multipoint communication server does not replicate the upstream media stream incoming from the second participant in order to avoid the first participant experimenting an echo and or a useless redundant sight of the second participant. The invention will now be illustrated by an embodiment relating to audio conferencing.

For example represent a multipoint audio conference between a plurality of conferencing endpoints distributed in four sites connected via internet through a multipoint communication server . The conferencing endpoints are smartphones located in a first site in a same room e.g. a meeting room in an office and are within earshot from each other. The conferencing endpoint is a mobile phone located in a second site the conferencing endpoints and are deskphones which are located in a third site and a fourth site.

Elements which are identical or similar will be designated by the same reference numerals throughout the drawings. illustrates that the conferencing endpoint is emitting an upstream voice stream to the multipoint communication server . The multipoint communication server replicates the upstream media stream in order to generate downstream media streams for the conferencing endpoints and which are not located in the second site as the conferencing device .

In an embodiment the list is periodically updated in order to determine if a conferencing endpoint is leaving the first site while keeping conferencing.

Therefore the list comprises the endpoint identifiers of the conferencing endpoints which are located in the first site which is in this example defined as the reach of the request . The list may further comprise endpoint identifiers of user devices which are not participating to the conference but which are also located in the first site .

The localization system may be implemented in various manners. For example the localization system broadcasts the request and receives the presence messages . For example the localization system uses eBeacon technology i.e. low power Bluetooth signals for broadcasting the request . In an embodiment the conferencing endpoint receives an identifier of the beacon and returns the presence message comprising both the UID and the identifier of the beacon . In such an embodiment the localization system receiving a plurality of presence messages from a plurality of conferencing endpoints generates a list of the UIDs associated to a same beacon identifier.

In other embodiments the beacon is optional and no request is sent. In such an embodiment the conferencing endpoints sent a respective presence message comprising both the UIDs and the respective position of the conferencing endpoints . The other functions of the localization system already described are unchanged.

A conferencing endpoint may be aware of its position thanks to Wi Fi or GPS signals. For example a conferencing endpoint may support an application for establishing a mapping of the near environment and then determine the position of each conferencing endpoint inside the environment by measures of level of power of emitted Wi Fi signals.

In such an example the processing unit receives endpoint identifiers associated to positions for example coordinates. The processing unit is configured to calculate a distance between two positions and in response to determining that the distance is lower than a threshold for example 2m to generate a list comprising the endpoint identifiers associated to the positions.

The multipoint communication server is configured to receive the list comprising the unique endpoints identifiers in order to avoid replicating an upstream voice stream received from an emitting endpoint in generated downstream voice streams for conferencing endpoints whose endpoint identifiers belong to the list namely for conferencing endpoints located in a same site as the emitting endpoint.

With reference to an example of an implementation of a multipoint communication server according to the invention will now be described. The multipoint communication server enables to establish a conference between six conferencing endpoints A B C D E and F represented both at the left and at the right of the multipoint communication server for the sake of clarity. The conferencing endpoints are represented at the left of the multipoint communication server for representing the upstream media streams and the conferencing endpoints are represented at the right of the multipoint communication server for representing the downstream media streams. The locations of the conferencing endpoints A and B are not determined in the multipoint communication server whereas the multipoint communication server identifies that the conferencing endpoints C and D are located in an area and the conferencing endpoints E and F are located in an area which is in another location than the area . For example the area is defined as the mutual earshot of two users respectively equipped with the conferencing endpoints C and D.

The conferencing endpoint A sends an upstream voice stream to the multipoint communication server which is represented by the dotted dashed line arrow. The conferencing endpoint B sends an upstream voice stream to the multipoint communication server which is represented by the dotted line arrow. The conferencing endpoint C sends an upstream voice stream to the multipoint communication server and the conferencing endpoint D sends an upstream voice stream to the multipoint communication server which is represented by the dashed line arrows. The conferencing endpoint E sends an upstream voice stream to the multipoint communication server and the conferencing endpoint F sends an upstream voice stream to the multipoint communication server which is represented by the solid line arrows.

The multipoint communication server is configured to determine that the endpoint identifiers of the conferencing endpoints C and D belong to a first list associated to the area and that the endpoint identifiers of the conferencing endpoints E and F belong to a second list associated to the area . Namely the multipoint communication server determines that the conferencing endpoints C and D are located in the area and the conferencing endpoints E and F are located in the area .

The multipoint communication server is configured to generate intermediary mixes by mixing together upstream voice streams incoming from conferencing endpoints which are located in the same area. Therefore the multipoint communication server mixes together the upstream voice streams and to generate an intermediary mix and the upstream voice streams and to generate an intermediary mix . Then the multipoint communication server is configured to generate a global mix by mixing together the intermediary mixes and and the upstream voice streams and . The global mix comprises all the emitted upstream voice streams and mixed together.

The multipoint communication server comprises or accesses a data repository in which is stored the following replication inhibition lists 

For the sake of clarity the downstream voice stream for a conferencing endpoint is numbered with the same numeral as the upstream voice stream incoming from the conferencing endpoint augmented by 100. The multipoint communication server is configured to generate a respective downstream voice stream for each conferencing endpoint by 

if the endpoint identifier of the conferencing endpoint does not belong to a list removing from the global mix the upstream voice stream incoming from the conferencing endpoint and if the endpoint identifier of the conferencing endpoint belongs to a list removing from the global mix the intermediary mix comprising the mixed upstream voice streams incoming from an area in which the conferencing endpoint is located.

For example as illustrated on the downstream voice stream generated for the conferencing endpoint A is generated by removing the upstream voice stream which is incoming from the conferencing endpoint A from the global mix as represented by the cross . Similarly the downstream voice stream generated for the conferencing endpoint B is generated by removing the upstream voice stream which is incoming from the conferencing endpoint B from the global mix . Similarly the downstream voice stream generated for the conferencing endpoint C is generated by removing from the global mix the intermediary mix whose mixed upstream voice streams and are incoming from the conferencing endpoints C and D of the area . Therefore the downstream voice stream and the downstream voice stream are identical and are generated by simply removing the intermediary mix from the global mix then by duplication. Similarly the downstream voice stream and the downstream voice stream are identical and are generated by simply removing the intermediary mix from the global mix then by duplication.

This implementation is particularly advantageous because the processing cost and time are reduced by removing only one intermediary mix instead of removing two independent upstream voice streams from the global mix.

There are various implementations of the multipoint communication server . In an embodiment described with reference to the multipoint communication server comprises a data repository a media processing unit and a control session interface . The control session interface communicates as represented by arrows with a session control unit . The session control unit manages the signalization for establishing call sessions between the participants of the conference. The media processing unit is driven by the control session interface which is called by the session control unit . The multipoint communication server further comprises a localization system interface which communicates with a localization system as represented by arrows.

In an alternative embodiment not represented the multipoint communication server may comprise the session control unit for controlling the multipoint communication session.

In an alternative embodiment not represented the multipoint communication server may comprise the localization system.

In an embodiment the participants of a call conference send directly their localization to the multipoint communication server . In such an embodiment the communication endpoints are configured to send a message comprising their location to the multipoint communication system based on Dual tone multi frequency signaling DTMF . In such an embodiment the session control unit is configured to play the role of the localization system .

In an embodiment the multipoint communication server may comprise an application server and a media server. The application server is configured to manage signalization streams for controlling a multipoint communication session between the conferencing endpoints and establishing audio or video calls. Signalizations streams may be based on various protocols. For example the formats of the signalization streams are according to the SIP protocol or Q.931 etc. A conferencing endpoint initiates an audio or video conference by sending a request for establishing call for example using SIP protocol to the application server. The multipoint communication server comprises a media server configured to process video streams i.e. to perform video conferencing tasks as video mixing video switching trans coding trans scaling or other manipulations on video streams. During a videoconference bidirectional communication channel is established between a media server and conferencing endpoints. Such a communication channel is able to carry a video stream in both directions. In use the communication channel carries the captured individual audio and or video stream from the conferencing endpoints to a media server in one direction and the generated audio and or video conference stream from a media server to the conferencing endpoints in the other direction. According to an embodiment of the invention the generated audio and or video conference stream for a conferencing endpoint does not replicate upstream audio and or video streams incoming from any conferencing endpoint belonging to the same area than the conferencing endpoint.

The media server is configured to manage namely mix audio and or video streams using for example Real Time Protocol RTP.

The application server invokes an application programming interface API. Then the media server request the API for allocating or deallocating audio and or video resources to an audio and or video call IP address RTP or RTCP ports etc. The API will create a conferencing routing map for the audio and or video streams. The API will manage the connection or disconnection of a call to the conference mute an upstream or a downstream media stream of a call and define the source area of a call.

In an embodiment the media server processes audio mixing by simply adding RTP packets received from each participant. At a time t the media server receives from each participant i a RTP packet which is encoded. The RTP packet is numerical. The media server decodes each packet in a same linear format for example by Pulse Code Modulation PCM. Therefore all the packets are same length vectors whose coefficients represents each both a sound and a level of power during a fixed duration.

For example a packet of an time t of a participant i is written as follows packet coefficient. 1 . . . coefficient. n wherein n represents the length of the vector.

The media server calculates a vectorial sum of all the packets received from the participants at the time t in order to generate a mixed packet 

For each participant i the media server generates a re encoded linear RTP packet downstream packet packetby subtracting from mixed packet all the packets packetfrom participants j belonging to a same replication inhibition set as the participant I including the case where j i.

For example a participant i does not belong to any replication inhibition set. The only packet to subtract from the global mix is the packetemitted by the participant i downstream packet packet packet coefficient. 1 coefficient. 1 . . . coefficient coefficient

For example a participant i belongs to a replication inhibition set. The packets to subtract from the global mix are the packetemitted by the participant i and the packets emitted by the participants belonging to the same replication inhibition set. For example only another participant w belongs to the replication inhibition set. A second packet to subtract is the packet packet 

Moreover the mix may only sum packets whose level of power is above a threshold and or higher than the mean of level of power of the packets.

Now with reference to the invention will now be illustrated by an embodiment relating to video conferencing. A multipoint communication server according to such an embodiment allows avoiding undesirable image redundancy between participants located in a mutual vision area. The participants use display screens for example the display screens of their laptops. In the pictured example the display screens are special glasses configured to display a video stream on a transparent glass in order to superimpose the video stream on the direct vision for the eyes of a user e.g. google Glasses . As pictured a first participant wears these special glasses a second participant not represented also wears special glasses and a third participant as well. The first participant and the third participant are in a mutual vision area whereas the second participant is located in another place which is not in the vision area of the first participant and third participant . A multipoint communication server according to the invention not represented suppress the picture of the third participant in the video stream intended to the first participant as shown by the cross while keeping the picture of the second participant. Indeed the multipoint communication server comprises a data repository in which is stored a replication inhibition list comprising identifiers of the special glasses of the first participant and third participant . Therefore the multipoint communication server allows avoiding undesirable image redundancy of the third participant for the first participant. Although the example pictured is very simple any number of participants may participate to the video conferencing. The multipoint communication server is configured to inhibit the replication of the video streams thanks to replication inhibition lists as described in the audio embodiments.

Now with reference to the invention will now be illustrated by an embodiment relating to a multilingual conference with a lecturer equipped with a microphone and two interpreters and each equipped with a headphone and a microphone. A multipoint communication server according to such an embodiment allows avoiding undesirable voice echo in another language than the chosen one for the participants in order to improve the concentration. For example the lecturer speaks in French language in his microphone. The first interpreter hears the French lecture in his headphone and translates the lecture in German language in real time through his microphone. The second interpreter hears the French lecture in his headphone and translates the lecture in English language in real time through his microphone. A plurality of participants to the conference are listening each the lecture thanks to headphones. The microphones and headphones are all connected through the multipoint communication server . Each participant chooses the language between French German and English on his headphone and the headphones are identified in a data repository of the multipoint communication server by headphones identifiers. For example the headphone of the first interpreter is identified by a headphone identifier i and the headphone of the second interpreter is identified by an headphone identifier i. The data repository comprises the headphones identifiers in association with the chosen language. For the sake of clarity a headphone identifier which is associated to the French language is identified by the letter f followed by a number. A headphone identifier which is associated to the English language is identified by the letter e followed by a number. A headphone identifier which is associated to the German language is identified by the letter g followed by a number.

The headphones identifiers are stored in the data repository in replication inhibition sets as a function of the associated chosen language as described in the following table 

For example a French voice stream is represented which is emitted from the lecturer to the multipoint communication server . The multipoint communication server is configured to replicate the French voice stream for each headphone whose headphone identifiers does not belong to the replication inhibition set as described by the arrows . The multipoint communication server is configured to inhibit the replication of the French voice stream for each headphone whose headphone identifiers belongs to the replication inhibition set as described by the crosses . For example the first interpreter receiving the replicated French voice stream transmits to the multipoint communication server a German voice stream which is a real time translation of the French voice stream . The headphone which is identified by the headphone identifier i belonging to the replication inhibition set the multipoint communication server is configured to inhibit the replication of the German voice stream as described by the cross . Hence the second interpreter is not disturbed by hearing both the French voice stream and the German voice stream .

Thanks to these features the same frequency bandwidth is used for all the languages with enables to save bandwidth.

The invention is not limited to the described embodiments. The appended claims are to be construed as embodying all modification and alternative constructions that may be occurred to one skilled in the art which fairly fall within the basic teaching here set forth. The use of the verb to comprise or to include and its conjugations does not exclude the presence of elements or steps other than those stated in a claim. Furthermore the use of the article a or an preceding an element or step does not exclude the presence of a plurality of such elements or steps. The invention may be implemented by means of hardware as well as software. The same item of hardware may represent several means .

The endpoints localization system multipoint communication server database described hereinabove may be implemented through the use of dedicated hardware as well as hardware capable of executing software in association with appropriate software. When provided by a processor the corresponding functions may be provided by a single dedicated processor by a single shared processor or by a plurality of individual processors some of which may be shared. Moreover explicit use of the term processor or controller should not be construed to refer exclusively to hardware capable of executing software and may implicitly include without limitation central processing unit CPU digital signal processor DSP hardware network processor application specific integrated circuit ASIC field programmable gate array FPGA read only memory ROM for storing software random access memory RAM and non volatile storage. Other hardware conventional and or custom may also be included. The endpoints call control server processing devices DVP system node registry task manager and database described hereinabove may be implemented in a unitary manner or in a distributed manner.

In the claims any reference signs placed between parentheses shall not be construed as limiting the scope of the claims.

