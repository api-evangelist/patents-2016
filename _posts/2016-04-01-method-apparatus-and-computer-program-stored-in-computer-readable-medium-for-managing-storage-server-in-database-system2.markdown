---

title: Method, apparatus, and computer program stored in computer readable medium for managing storage server in database system
abstract: Disclosed is a method of managing a storage server in a database system. Provided is a storage server including a cache device to store at least one block that includes data; a permanent storage medium to record the at least one block stored in the cache device; and a controller to record the at least one block stored in the cache device in the permanent storage medium, wherein the controller includes a grade determiner to determine a grade of each of the at least one block based on a size of each of the at least one block; a victim block determiner to determine a victim block to be recorded in the permanent storage medium among blocks stored in the cache device based on the determined grade of each of the at least one block; and a block recorder to record the determined victim block in the permanent storage medium.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09600415&OS=09600415&RS=09600415
owner: 
number: 09600415
owner_city: 
owner_country: 
publication_date: 20160401
---
This application claims priority to and the benefit of Korean Patent Application No. 10 2016 0023056 filed in the Korean Intellectual Property Office on Feb. 26 2016 the entire contents of which are incorporated herein by reference.

The present disclosure relates to a method of managing a storage server in a database system and more particularly a method of efficiently managing a cache device.

A database system may collect store manage and analyze data. Recently technology for a mass database management system such as big data processing of extracting a large set of structured or unstructured data and a value from such data and analyzing a result is in development.

In the case of performing a database operation the database system operates in a cache device to decrease an input output I O time. For example when a database server is to change data recorded in a storage server the database server loads data from the storage server stores the loaded data in the cache device changes an object stored in the cache device and applies the changed data to the storage server.

With a large capacity of a database ongoing the storage server has become to include a large amount of data. Accordingly technology for a method of managing a large amount of data in the storage server is required.

The present disclosure has been conceived to outperform the aforementioned related art and thus has been made in an effort to provide a method of efficiently managing data in a database system.

An exemplary embodiment of the present disclosure provides a storage server including a cache device to store at least one block that includes data a permanent storage medium to record the at least one block stored in the cache device and a controller to record the at least one block stored in the cache device in the permanent storage medium wherein the controller includes a grade determiner to determine a grade of each of the at least one block based on a size of each of the at least one block a victim block determiner to determine a victim block to be recorded in the permanent storage medium among blocks stored in the cache device based on the determined grade of each of the at least one block and a block recorder to record the determined victim block in the permanent storage medium.

Another exemplary embodiment of the present disclosure provides a database management program including instructions stored in a computer readable medium to control a computer to perform the following operations wherein the operations include an operation of determining a grade of each of at least one block based on a size of each of the at least one block each of the at least one block including data and the at least one block being stored in a cache device an operation of determining a victim block to be recorded in a permanent storage medium among blocks stored in the cache device based on the determined grade of each of the at least one block and an operation of recording the determined victim block in the permanent storage medium.

Still another exemplary embodiment of the present disclosure provides a database management method including determining a grade of each of at least one block based on a size of each of the at least one block each of the at least one block including data and the at least one block being stored in a cache device determining a victim block to be recorded in a permanent storage medium among blocks stored in the cache device based on the determined grade of each of the at least one block and recording the determined victim block in the permanent storage medium.

According to exemplary embodiments of the present disclosure there is provided a method of efficiently managing data in a data system.

Various exemplary embodiments are described with reference to the accompanying drawings in which like reference numerals refer to like constituent elements throughout. In the present specification various descriptions are provided to help understand the present disclosure. However it is apparent that the exemplary embodiments may be implemented without the detailed descriptions. In other examples known structures and apparatuses are provided in a block diagram form to help the description of the exemplary embodiments.

The terms component module system and the like used in the present specification refer to a computer related entity hardware firmware software a combination of software and hardware or execution of software. For example the component may be a processing process executed on a processor the processor an object an execution thread a program and or a computer however the present disclosure is not limited thereto. For example any of an application executed on a computing device and the computing device may be the component. At least one component may be present in the processor and or the execution thread at all times. A single component may be localized in a single computer or may be distributed between two or more computers. Also the components may be executed from various computer readable media having various data structures stored therein. For example the components may communicate through local and or remote processes according to a signal for example data through a network such as another system and the Internet through data and or a signal from a single component that interacts with another component in a local system and a distributed system having one or more data packets.

In the present specification a database indicates a system that stores related data in a form to be capable of being processed by a computer. The database may manage data and answer a question of a user and data stored in the database may be changed. The database may store new data and may perform an operation of deleting and changing the existing data.

In the present specification a transaction indicates a continuous processing unit about a series of operations such as exchange of information database update and the like. The transaction may be defined as a basic unit of an operation for completing a requested operation in a state in which integrity of the database is guaranteed.

In the present specification a block may indicate a chunk of data. For example the block may include a single table in which data is stored and may include a plurality of tables. The block may have various sizes. For example the block may have sizes of 10 kb 100 kb 1 megabyte 2 megabytes 3 megabytes 4 megabytes and the like however the present disclosure is not limited thereto.

In the present specification flushing indicates an operation of determining a victim block among blocks stored in a cache device and recording the determined victim block in a permanent storage medium .

In the present specification a dirty block indicates a block in which data included in the permanent storage medium does not match data included in the cache device . A clean block indicates a block in which data included in the permanent storage medium matches data included in the cache device . A victim block indicates at least a portion of blocks selected for flushing from dirty blocks.

Description related to the proposed exemplary embodiments is provided for those skilled in the art to use or implement the present disclosure. It will be apparent to those skilled in the art that various modifications may be made to the exemplary embodiments. General principles defined herein may be applicable to other exemplary embodiments without departing from the scope of the present disclosure. Accordingly the present disclosure is not limited thereto and should be interpreted within the widest scope consistent with the proposed principles and new features.

Hereinafter exemplary embodiments of the present disclosure will be described in detail with reference to the accompanying drawings.

The database server may include a predetermined type of a computer system or a computer device such as a microprocessor a main frame computer a digital single processor a portable device a device controller and the like.

A client may indicate nodes in a database system having a mechanism for communication through a network. For example the client may include a personal computer PC a laptop computer a workstation a terminal and or a predetermined electronic device having network accessibility. Also the client may include a predetermined server configured by at least one of an agent an application programming interface API and a plug in.

The database server may include a memory not shown . The database server may perform a database operation using the memory. For example when the database server performs a transaction the database server may load data from the storage server and may store the loaded data in at least a portion of the memory not shown .

The memory not shown may indicate a volatile storage device that s a primary storage device directly accessed by a processor such as random access memory RAM such as dynamic RAM DRAM static RAM SRAM and the like and in which stored information is momentarily erased if power is off however the present disclosure is not limited thereto. The memory may operate by the processor.

The database server may be connected to the storage server over a network. The network may include a wired network and a wireless network however the present disclosure is not limited thereto.

The storage server indicates a server capable of continuously storing data. The database server may include the cache device and the permanent storage medium .

The cache device may include a semiconductor based storage device capable of continuously storing data. For example the cache device may include a solid state disk or a solid state drive SSD a flash memory and the like however the present disclosure is not limited thereto.

The permanent storage medium may include a non volatile storage medium capable of continuously storing data. For example the permanent storage medium may include a storage device based on a flash memory and or a battery backup memory in addition to a disk an optical disc and a magneto optical storage device however the present disclosure is not limited thereto.

The cache device may have relatively excellent write and read performance compared to that of the permanent storage medium .

When a request for storing a block is received from the database server the storage server may store the block received from the database server in the cache device having the relatively excellent write and read performance. In this case the database server may recognize that the block is stored.

To preserve the block stored in the cache device the storage server may record the block in the permanent storage medium before deleting the block stored in the cache device due to a limited space of the cache device .

When recording the block in the permanent storage medium the storage server may determine a grade of each of the blocks based on a size of each of the blocks stored in the cache device . Also the storage server may determine a victim block to be recorded in the permanent storage medium among the blocks stored in the cache device by applying a different policy based on the determined grade and may efficiently record the determined victim block in the permanent storage medium .

The storage server may improve the usability of the cache device and the permanent storage medium by determining the grade of each of the blocks stored in the cache device by determining the victim block based on the different policy corresponding to the determined grade and by efficiently recording the determined victim block in the permanent storage medium .

The storage server may include a transmission and reception module the cache device the permanent storage medium and a controller .

The transmission and reception module may receive a block from the database server . Also the transmission and reception module may transmit a block read from the cache device or the permanent storage medium to the database server .

The cache device may store the block received at the transmission and reception module . For example the storage server may store the block received from the database server in the cache device .

The cache device may include a semiconductor based storage device capable of continuously storing data. For example the cache device may include an SSD a flash memory and the like however the present disclosure is not limited thereto.

The permanent storage medium may record the block stored in the cache device . For example the storage server may record the block stored in the cache device in the permanent storage medium . Once the block is recorded in the permanent storage medium the storage server may store another block at a position at which the block of the cache device is stored.

For example once a first block is recorded in the permanent storage medium the storage server may store another block at a position at which the first block of the cache device is stored.

The permanent storage medium indicates a non volatile storage medium capable of continuously storing data. For example the permanent storage medium may include a storage device based on a flash memory and or a battery backup memory in addition to a disk an optical disc and a magneto optical storage device.

The controller may include a record determiner a grade determiner a victim block determiner and a block recorder . The record determiner the grade determiner the victim block determiner and the block recorder may be configured by a single processor. Each thereof may be configured by a single processor however the present disclosure is not limited thereto.

The controller may manage data stored in the cache device based on a block unit. For example the controller may manage a single set of table data as a single block and may manage a plurality of sets of table data as a single block however the present disclosure is not limited thereto.

The record determiner may determine whether to record at least one block stored in the cache device in the permanent storage medium . The record determiner may determine whether to record at least one block stored in the cache device in the permanent storage medium based on at least one of an input of a user a usage amount of the permanent storage medium a usage amount of the cache device the number of dirty blocks and the number of clean blocks.

For example when the usage amount of the permanent storage medium is less than a threshold value the record determiner may determine to record at least one block stored in the cache device in the permanent storage medium .

When the usage amount of the cache device is greater than or equal to a threshold value the record determiner may determine to record at least one block stored in the cache device in the permanent storage medium .

The record determiner may determine at least one block stored in the cache device in the permanent storage medium based on the input of the user.

When the number of clean blocks is less than a threshold value the record determiner may determine to record at least one block stored in the cache device in the permanent storage medium .

When the number of dirty blocks is greater than or equal to a threshold value the record determiner may determine to record at least one block stored in the cache device in the permanent storage medium .

The record determiner may determine to record at least one block stored in the cache device in the permanent storage medium based on a combination of the aforementioned examples.

The grade determiner may determine a grade of each of the blocks stored in the cache device based on a size of a block.

The grade determiner may predetermine a grade decision standard. For example the grade determiner may predetermine the grade decision standard based on the input of the user and may predetermine the grade decision standard based on information received from an external device however the present disclosure is not limited thereto.

The grade determiner may automatically determine the grade decision standard without the input of the user or information received from the external device. For example the grade determiner may automatically determine the grade decision standard based on performance when the block is recorded in the permanent storage medium . For example in a case in which a performance difference occurs based on a predetermined size when the block is recorded in the permanent storage medium the grade determiner may determine a value indicating the predetermined size as the grade decision standard.

The grade determiner may determine the grade of the block based on the determined grade decision standard and the size of the block. For example the grade determiner may determine a grade of a block having a size greater than the grade decision standard as a large grade and may determine a grade of a block having a size less than the grade decision standard as a small grade.

The grade determiner may determine the grade of the block as a small grade a middle grade or a large grade based on two threshold values. Without being limited thereto the grade determiner may determine the grade of the block using various grades.

According to another exemplary embodiment of the present disclosure the grade determiner may define a new block by combining a plurality of small grade blocks. Also when a size of the new block is greater than the grade decision standard the grade determiner may determine the new block as the large grade.

The victim block determiner may determine a victim block to be recorded in the permanent storage medium among blocks stored in the cache device based on the determined grade of each of the blocks.

The victim block determiner may determine the victim block by applying a different policy based on the determined grade.

With respect to blocks determined as the large grade the victim block determiner may determine the victim block based on order in which the blocks are used. For example with respect to the blocks determined as the large grade the victim block determiner may determine as the victim block a block having a longest use history.

In this case the victim block determiner may determine the number of victim blocks based on at least one of the usage amount of the cache device the usage amount of the permanent storage medium the number of dirty blocks and the number of clean blocks.

When the usage amount of the cache device is relatively great when the usage amount of the permanent storage medium is relatively small when the number of clean blocks is relatively small when the number of dirty blocks is relatively large or when the combination thereof occurs the victim block determiner may increase the number of victim blocks thereby efficiently managing the cache device .

With respect to blocks determined as the small grade the victim block determiner may determine the victim block based on positions at which the blocks determined as the small grade are to be recorded within the permanent storage medium .

For example the victim block determiner may group blocks determined as the small grade into at least one group based on physical recording positions within the permanent storage medium . For example the victim block determiner may determine as a single group blocks of which recording positions within the permanent storage medium are separate at a distance within a threshold value. Also the victim block determiner may determine as a single group blocks to be recorded in a specific area of the permanent storage medium .

The victim block determiner may determine as victim blocks blocks included in at least one group among the determined groups.

In this case the block recorder may record blocks included in the same group in the same time interval. For example when blocks included in a first group are determined as victim blocks the storage server may record the blocks included in the first group in the permanent storage medium in the same time interval.

The storage server may improve the performance of a recording operation of the storage server by recording blocks having adjacent recording positions within the permanent storage medium in the same time interval.

According to another exemplary embodiment of the present disclosure the victim block determiner may determine the victim block based on at least one of the usage amount of the permanent storage medium and the usage amount of the cache device and the determined grade of the block.

For example when the usage amount of the permanent storage medium is less than a threshold value the victim block determiner may increase a ratio of the large grade among victim blocks. Also when the usage amount of the cache device is greater than or equal to a threshold value the victim block determiner may increase a ratio of the large grade among the victim blocks. Also when the usage amount of the permanent storage medium is less than a threshold value and the usage amount of the cache device is greater than or equal to the threshold value the victim block determiner may increase a ratio of the large grade among the victim blocks.

The victim block determiner may quickly record a block in the permanent storage medium and may quickly secure a room of the cache device by increasing a ratio of the large grade among the victim blocks.

The block recorder may record the determined victim blocks among the blocks stored in the cache device in the permanent storage medium .

In this case the block recorder may record blocks included in the same group among small grade blocks in the same time interval. For example when blocks included in the first group among the small grade blocks are determined as victim blocks the block recorder may record the blocks included in the first group in the permanent storage medium in the same time interval.

The storage server may determine as clean blocks blocks recorded in the permanent storage medium among blocks stored in the cache device . Also the storage server may store another block received from the database server at a position of a block determined as the clean block among the blocks included in the cache device .

According to another exemplary embodiment of the present disclosure the record determiner the grade determiner the victim block determiner and the block recorder of the storage server may be positioned outside the storage server . For example the record determiner the grade determiner the victim block determiner and the block recorder of the storage server may be positioned in the database server and may be positioned outside the database system however the present disclosure is not limited thereto.

In operation S the storage server may determine whether to record at least one block stored in the cache device in the permanent storage medium .

The storage server may determine whether to record at least one block stored in the cache device in the permanent storage medium based on at least one of an input of a user a usage amount of the permanent storage medium a usage amount of the cache device the number of dirty blocks and the number of clean blocks.

For example when the usage amount of the permanent storage medium is less than a threshold value the storage server may determine to record at least one block stored in the cache device in the permanent storage medium .

When the usage amount of the cache device is greater than or equal to a threshold value the storage server may determine to record at least one block stored in the cache device in the permanent storage medium .

The storage server may determine at least one block stored in the cache device in the permanent storage medium based on the input of the user.

When the number of clean blocks is less than a threshold value the storage server may determine to record at least one block stored in the cache device in the permanent storage medium .

When the number of dirty blocks is greater than or equal to a threshold value the storage server may determine to record at least one block stored in the cache device in the permanent storage medium .

The storage server may determine to record at least one block stored in the cache device in the permanent storage medium based on a combination of the aforementioned examples.

In operation S the storage server may determine a grade of each of the blocks stored in the cache device based on a size of a block.

The storage server may predetermine a grade decision standard. For example the storage server may predetermine the grade decision standard based on the input of the user and may predetermine the grade decision standard based on information received from an external device however the present disclosure is not limited thereto.

The storage server may automatically determine the grade decision standard without the input of the user or information received from the external device. For example the storage server may automatically determine the grade decision standard based on performance when the block is recorded in the permanent storage medium . For example in a case in which a performance difference occurs based on a predetermined size when the block is recorded in the permanent storage medium the storage server may determine a value indicating the predetermined size as the grade decision standard.

The storage server may determine the grade of the block based on the determined grade decision standard and the size of the block. For example the storage server may determine a grade of a block having a size greater than the grade decision standard as a large grade and may determine a grade of a block having a size less than the grade decision standard as a small grade.

The storage server may determine the grade of the block as a small grade a middle grade or a large grade based on two threshold values. Without being limited thereto the storage server may determine the grade of the block using various grades.

According to another exemplary embodiment of the present disclosure the storage server may define a new block by combining a plurality of small grade blocks. Also when a size of the new block is greater than the grade decision standard the storage server may determine the new block as the large grade.

In operation S the storage server may determine a victim block to be recorded in the permanent storage medium among blocks stored in the cache device based on the determined grade of each of the blocks.

The storage server may determine the victim block by applying a different policy based on the determined grade.

With respect to blocks determined as the large grade the storage server may determine the victim block based on order in which the blocks are used. For example with respect to the blocks determined as the large grade the storage server may determine as the victim block a block having a longest use history.

In this case the storage server may determine the number of victim blocks based on at least one of the usage amount of the cache device the usage amount of the permanent storage medium the number of dirty blocks and the number of clean blocks.

When the usage amount of the cache device is relatively great when the usage amount of the permanent storage medium is relatively small when the number of dirty blocks is relatively large when the number of clean blocks is relatively small or when the combination thereof occurs the storage server may increase the number of victim blocks thereby efficiently managing the cache device .

With respect to blocks determined as the small grade the storage server may determine the victim block based on positions at which the blocks determined as the small grade are to be recorded within the permanent storage medium .

For example the storage server may group blocks determined as the small grade into at least one group based on physical recording positions within the permanent storage medium . For example the storage server may determine as a single group blocks of which recording positions within the permanent storage medium are separate at a distance within a threshold value. Also the storage server may determine as a single group blocks to be recorded in a specific area of the permanent storage medium .

The storage server may determine as victim blocks blocks included in at least one group among the determined groups.

In this case the storage server may record blocks included in the same group in the same time interval. For example when blocks included in a first group are determined as victim blocks the storage server may record the blocks included in the first group in the permanent storage medium in the same time interval.

The storage server may improve the performance of a recording operation of the storage server by recording blocks having adjacent recording positions within the permanent storage medium in the same time interval.

According to another exemplary embodiment of the present disclosure the storage server may determine the victim block based on at least one of the usage amount of the permanent storage medium and the usage amount of the cache device and the determined grade of the block.

For example when the usage amount of the permanent storage medium is less than a threshold value the storage server may increase a ratio of the large grade among victim blocks. Also when the usage amount of the cache device is greater than or equal to a threshold value the storage server may increase a ratio of the large grade among the victim blocks. Also when the usage amount of the permanent storage medium is less than a threshold value and the usage amount of the cache device is greater than or equal to the threshold value the storage server may increase a ratio of the large grade among the victim blocks.

The storage server may quickly record a block in the permanent storage medium and may quickly secure a room of the cache device by increasing a ratio of the large grade among the victim blocks.

In operation S the storage server may record the determined victim block in the permanent storage medium .

The storage server may record the determined victim blocks among the blocks stored in the cache device in the permanent storage medium .

In this case the storage server may record blocks included in the same group among small grade blocks in the same time interval. For example when blocks included in the first group among the small grade blocks are determined as victim blocks the storage server may record the blocks included in the first group in the permanent storage medium in the same time interval.

The storage server may determine as clean blocks blocks recorded in the permanent storage medium among blocks stored in the cache device . Also the storage server may store another block received from the database server at a position of a block determined as the clean block among the blocks included in the cache device .

According to another exemplary embodiment of the present disclosure the aforementioned exemplary embodiments may be performed by the database server .

In operation S the database server may determine whether to record at least one block stored in the cache device in the permanent storage medium .

The database server may determine whether to record at least one block stored in the cache device in the permanent storage medium based on at least one of an input of a user a usage amount of the permanent storage medium a usage amount of the cache device the number of dirty blocks and the number of clean blocks.

For example when the usage amount of the permanent storage medium is less than a threshold value the database server may determine to record at least one block stored in the cache device in the permanent storage medium .

When the usage amount of the cache device is greater than or equal to a threshold value the database server may determine to record at least one block stored in the cache device in the permanent storage medium .

The database server may determine at least one block stored in the cache device in the permanent storage medium based on the input of the user.

When the number of clean blocks is less than a threshold value the database server may determine to record at least one block stored in the cache device in the permanent storage medium .

When the number of dirty blocks is greater than or equal to a threshold value the database server may determine to record at least one block stored in the cache device in the permanent storage medium .

The database server may determine to record at least one block stored in the cache device in the permanent storage medium based on a combination of the aforementioned examples.

In operation S the database server may determine a grade of each of the blocks stored in the cache device based on a size of a block.

The database server may predetermine a grade decision standard. For example the database server may predetermine the grade decision standard based on the input of the user and may predetermine the grade decision standard based on information received from an external device however the present disclosure is not limited thereto.

The database server may automatically determine the grade decision standard without the input of the user or information received from the external device. For example the database server may automatically determine the grade decision standard based on performance when the block is recorded in the permanent storage medium . For example in a case in which a performance difference occurs based on a predetermined size when the block is recorded in the permanent storage medium the database server may determine a value indicating the predetermined size as the grade decision standard.

The database server may determine the grade of the block based on the determined grade decision standard and the size of the block. For example the database server may determine a grade of a block having a size greater than the grade decision standard as a large grade and may determine a grade of a block having a size less than the grade decision standard as a small grade.

The database server may determine the grade of the block as a small grade a middle grade or a large grade based on two threshold values. Without being limited thereto the database server may determine the grade of the block using various grades.

According to another exemplary embodiment of the present disclosure the database server may define a new block by combining a plurality of small grade blocks. Also when a size of the new block is greater than the grade decision standard the database server may determine the new block as the large grade.

In operation S the database server may determine a victim block to be recorded in the permanent storage medium among blocks stored in the cache device based on the determined grade of each of the blocks.

The database server may determine the victim block by applying a different policy based on the determined grade.

With respect to blocks determined as the large grade the database server may determine the victim block based on order in which the blocks are used. For example with respect to the blocks determined as the large grade the database server may determine as the victim block a block having a longest use history.

In this case the database server may determine the number of victim blocks based on at least one of the usage amount of the cache device the usage amount of the permanent storage medium the number of dirty blocks and the number of clean blocks.

When the usage amount of the cache device is relatively great when the usage amount of the permanent storage medium is relatively small when the number of dirty blocks is relatively large when the number of clean blocks is relatively small or when the combination thereof occurs the database server may increase the number of victim blocks thereby efficiently managing the cache device .

With respect to blocks determined as the small grade the database server may determine the victim block based on positions at which the blocks determined as the small grade are to be recorded within the permanent storage medium .

For example the database server may group blocks determined as the small grade into at least one group based on physical recording positions within the permanent storage medium . For example the database server may determine as a single group blocks of which recording positions within the permanent storage medium are separate at a distance within a threshold value. Also the database server may determine as a single group blocks to be recorded in a specific area of the permanent storage medium .

The database server may determine as victim blocks blocks included in at least one group among the determined groups.

In this case the database server may record blocks included in the same group in the same time interval. For example when blocks included in a first group are determined as victim blocks the database server may record the blocks included in the first group in the permanent storage medium in the same time interval.

The database server may improve the performance of a recording operation of the storage server by recording blocks having adjacent recording positions within the permanent storage medium in the same time interval.

According to another exemplary embodiment of the present disclosure the database server may determine the victim block based on at least one of the usage amount of the permanent storage medium and the usage amount of the cache device and the determined grade of the block.

For example when the usage amount of the permanent storage medium is less than a threshold value the database server may increase a ratio of the large grade among victim blocks. Also when the usage amount of the cache device is greater than or equal to a threshold value the database server may increase a ratio of the large grade among the victim blocks. Also when the usage amount of the permanent storage medium is less than a threshold value and the usage amount of the cache device is greater than or equal to the threshold value the database server may increase a ratio of the large grade among the victim blocks.

The database server may quickly record a block in the permanent storage medium and may quickly secure a room of the cache device by increasing a ratio of the large grade among the victim blocks.

In operation S the database server may record the determined victim block in the permanent storage medium .

The database server may record the determined victim blocks among the blocks stored in the cache device in the permanent storage medium .

In this case the database server may record blocks included in the same group among small grade blocks in the same time interval. For example when blocks included in the first group among the small grade blocks are determined as victim blocks the database server may record the blocks included in the first group in the permanent storage medium in the same time interval.

The database server may determine as clean blocks blocks recorded in the permanent storage medium among blocks stored in the cache device . Also the database server may store another block at a position of a block determined as the clean block among the blocks included in the cache device .

With respect to blocks determined as the small grade the storage server may determine a victim block based on recording positions of the blocks determined as the small grade within the permanent storage medium .

For example the storage server may classify blocks determined as the small grade into at least one group based on a physical recording position within the permanent storage medium . For example the storage server may determine as a first group blocks to be recorded in a first area within the permanent storage medium among blocks included in the cache device . Also the storage server may determine as a second group blocks to be recorded in a second area within the permanent storage medium among blocks included in the cache device .

The storage server may determine as victim blocks blocks included in at least one group among determined groups. For example the storage server may determine blocks to be included in the first group as victim blocks.

The storage server may record blocks included in the same group in the same time interval. For example when the blocks included in the first group are determined as the victim blocks the storage server may record the blocks included in the first group in the first area of the permanent storage medium in the same time interval.

The storage server may record blocks having adjacent recording positions within the permanent storage medium in the same time interval thereby improving the performance of a recording operation of the storage server .

The storage server may determine whether to perform flushing based on at least one of an input of a user a usage amount of the permanent storage medium a usage amount of the cache device the number of dirty blocks and the number of clean blocks. In this case flushing indicates an operation of recording at least one block stored in the cache device in the permanent storage medium .

In operation S the storage server may determine whether a flushing request is received from the user. When the flushing request is received from the user the storage server may perform flushing in operation S. When the flushing request is not received from the user the storage server may perform operation S. Flushing indicates an operation of determining a victim block among blocks stored in the cache device and recording the determined victim block in the permanent storage medium .

In operation S the storage server may determine whether a value indicating the usage amount of the permanent storage medium is less than a threshold value. In this case the storage server may determine the threshold value based on information received from the user may determine the threshold value based on information received from an external device and without being limited thereto may determine the threshold value using various methods.

When a value indicating the usage amount of the permanent storage medium is less than the threshold value the storage server may perform flushing in operation S. Also when the value indicating the usage amount of the permanent storage medium is greater than or equal to the threshold value the storage server may perform operation S.

In operation S the storage server may determine whether a value indicating the usage amount of the cache device is greater than or equal to a threshold value. In this case the storage server may determine the threshold value based on information received from the user may determine the threshold value based on information received from the external device and without being limited thereto may determine the threshold value using various methods.

When the value indicating the usage amount of the cache device is greater than or equal to the threshold value the storage server may perform flushing in operation S. Also when the value indicating the usage amount of the cache device is less than the threshold value the storage server may not perform flushing.

In operation S the storage server may perform flushing. The flushing method is described above with .

The exemplary embodiments of the present disclosure may be configured in a form of a recording medium including instructions executable by a computer such as a program module executed by the computer. Computer readable media may be available media accessible by the computer and include all of volatile and non volatile media and separable and inseparable media. Also the computer readable media may include temporary recordable media and non temporary recordable media.

The computer readable media may include all of computer storage media and communication media. The computer storage media include all of volatile and non volatile media and separable and inseparable media configured with a computer readable instruction a data structure a program module or a method or technology for storing information such as other data. The communication media typically include a computer readable instruction a data structure a program module or other data of a modulated data signal such as a carrier or other transmission mechanisms and include information transfer media.

The aforementioned description of the present disclosure is provided as an example and it will be apparent to those skilled in the art that various modifications and changes may be made without departing from the scope and spirit of the present disclosure. Therefore it should be understood that the above embodiments are not limitative but illustrative in all aspects. For example each constituent element described in a singular form may be distributed and thereby implemented. Similarly constituent elements described to be distributive may be implemented in a combined form.

The scope of the present disclosure is defined by the appended claims rather than by the description preceding them and therefore all changes and modifications that fall within metes and bounds of the claims or equivalents of such metes and bounds are therefore intended to be embraced by the claims.

