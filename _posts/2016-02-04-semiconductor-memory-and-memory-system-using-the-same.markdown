---

title: Semiconductor memory and memory system using the same
abstract: A semiconductor memory includes a memory block configured to perform an operation according to a first test pattern or a second test pattern, a switching circuit configured to provide the first test pattern or the second test pattern to the memory block according to a first test mode signal and a second test mode signal, and a test pattern setup circuit configured to store a test pattern source signal in a feedback loop varied according to a third test mode signal and output the stored test pattern source signal as the first test pattern.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09502136&OS=09502136&RS=09502136
owner: SK HYNIX INC.
number: 09502136
owner_city: Icheon-Si
owner_country: KR
publication_date: 20160204
---
This application claims priority under 35 U.S.C. 119 a to Korean application No. 10 2015 0131399 filed on Sep. 17 2015 in the Korean intellectual property Office which is incorporated by reference in its entirety as set forth in full.

The inventive concept relates to a semiconductor integrated circuit and more particularly to a semiconductor memory and a memory system using the same.

Semiconductor apparatuses may be configured in a structure in which a plurality of semiconductor chips are two dimensionally arranged or three dimensionally stacked.

The plurality of semiconductor chips may be channels which use individual data input output I O pads. That is the semiconductor apparatus may include a plurality of channels.

A test for verifying whether or not an operation of the semiconductor apparatus is normally performed may be inevitably performed.

However since the number of channels which can be tested once in the test equipment is limited the test equipment has to sequentially test the plurality of channels using the same test pattern regardless of an actual operation environment and thus test versatility and test performance may be reduced.

According to an embodiment there is provided a semiconductor memory. The semiconductor memory may include a memory block configured to perform an operation according to a first test pattern or a second test pattern. The semiconductor memory may also include a switching circuit configured to provide the first test pattern or the second test pattern to the memory block according to a first test mode signal and a second test mode signal. The semiconductor memory may also include a test pattern setup circuit configured to store a test pattern source signal in a feedback loop varied according to a third test mode signal and output the stored test pattern source signal as the first test pattern.

According to an embodiment there is provided a memory system. The memory system may include a plurality of channels. The memory system may be configured to operate remaining channels according to a first test pattern other than one channel among the plurality of channels and allow the one channel to perform a test operation according to a second test pattern.

Hereinafter various embodiments will be described in greater detail with reference to the accompanying figures. Various embodiments are described herein with reference to cross sectional illustrations that are schematic illustrations of embodiments and intermediate structures . As such variations from the shapes of the illustrations as a result for example of manufacturing techniques and or tolerances are to be expected. Thus embodiments should not be construed as limited to the particular shapes of regions illustrated herein but may be to include deviations in shapes that result for example from manufacturing. In the figures lengths and sizes of layers and regions may be exaggerated for clarity. Like reference numerals in the figures denote like elements. It is also understood that when a layer is referred to as being on another layer or substrate it can be directly on the other or substrate or intervening layers may also be present. One or more various embodiments are provided to a semiconductor memory and a memory system capable of improving test performance.

The inventive concept is described herein with reference to cross section and or plan illustrations that are schematic illustrations of idealized embodiments of the inventive concept. However embodiments of the inventive concept should not be limited construed as limited to the inventive concept. Although a few embodiments of the inventive concept will be shown and described it will be appreciated by those of ordinary skill in the art that changes may be made in these embodiments without departing from the principles and spirit of the inventive concept.

Referring to a memory system according to an embodiment of the inventive concept may include a plurality of semiconductor chips to . In an embodiment the plurality of semiconductor chips to may be provided in one package PKG which may be configured as a circuit. In an embodiment the plurality of semiconductor chips to may be provided in two or more packages.

An address signal ADD a command signal CMD and a clock signal CLK may be commonly provided to the plurality of semiconductor chips to .

Chip select signals CS  to CS  and reset signals RST b to REST b may be independently provided to the plurality of semiconductor chips to respectively.

Each of the plurality of semiconductor chips to may be activated through a chip select signal corresponding thereto among the chip select signals CS  to CS .

Each of the plurality of semiconductor chips to may be initialized by a reset signal corresponding thereto among the reset signals RST b to RST b.

The plurality of semiconductor chips to may receive the command signal CMD the address signal ADD the clock signal CLK the chip select signals CS  to CS  and the reset signals RST b to REST b from an external apparatus. The external apparatus may be for example a controller such as a central processing unit CPU or a graphic processing unit GPU .

The plurality of semiconductor chips to may include individual data input output I O terminals DQ and may be configured to perform independent operations. In an embodiment each of the plurality of semiconductor chips to may correspond to one channel. In an embodiment the plurality of semiconductor chips to may refer to first to fourth channels CH to CH.

In the memory system according to an embodiment the first to fourth channels CH to CH may be configured to be simultaneously operated using different test patterns.

The test pattern may be refer to a pattern that a combination of the command signal CMD the address signal ADD and the chip select signals CS  to CS  may be sequentially repeated the predetermined number of times.

The memory system may be configured to store a first test pattern by previously programming different test patterns with respect to the first to fourth channels CH to CH. The memory system may also perform a test based on a second test pattern on a desired channel among the first to fourth channels CH to CH. The memory system may also repeatedly perform a dummy operation based on the first test pattern on the remaining channels while the test is performed.

The first test pattern may be not a test pattern for an actual test but a test pattern for the dummy operation. Further the first test pattern may refer to a dummy test pattern. The second test pattern may be a test pattern for the actual test which is input from the outside of the memory system in real time. In addition the second test pattern may refer to an external test pattern.

The reliability of the test on the memory system may be increased as the test pattern is equally to the actual operation environment.

However due to the physical limitation of the test equipment in the actual test environment the test is performed on any one among the first to fourth channels CH to CH and any operation may be performed on the remaining channels.

Accordingly the memory system according to an embodiment may perform a test which performs actual data I O on one channel among the first to fourth channels CH to CH by providing a test pattern to the one channel. The memory system may also perform a dummy operation similar to the actual operation environment on the remaining channels using different dummy test patterns which are previously programmed. Further a detailed description thereof will be made with reference to the accompanying figures below.

Referring to the semiconductor chip that is the first channel CH may include a memory block a test pattern setup unit and a switching unit .

The memory block may be configured to perform an operation for example a read operation a write operation a precharge operation and the like according to a first test pattern that is the dummy test pattern or the second test pattern that is the external test pattern .

An internal command signal iCMD an internal address signal iADD and an internal chip selection signal iCS  as the external test pattern or the dummy test pattern may be provided to the memory block .

The switching unit may be configured to provide the external test pattern or the dummy test pattern to the memory block according to a first test mode signal TM PGM and a second test mode signal TM PTN.

The first to third demultiplexers to may output the command signal CMD the address signal ADD and the chip selection signal CS  as the test pattern source signal or the external test pattern according to the first test mode signal TM PGM.

For example when the first test mode signal TM PGM is a high level the first to third demultiplexers to may provide the command signal CMD the address signal ADD and the chip selection signal CS  as the test pattern source signal to the test pattern setup unit .

When the first test mode signal TM PGM is a low level the first to third demultiplexers to may provide the command signal CMD the address signal ADD and the chip selection signal CS  as the external test pattern to the first to third multiplexers to .

The first demultiplexer may provide the command signal CMD to the test pattern setup unit when the first test mode signal TM PGM is the high level. The first demultiplexer may also provide the command signal CMD to the first multiplexer when the first test mode signal TM PGM is the low level.

The second demultiplexer may provide the address signal ADD to the test pattern setup unit when the first test mode signal TM PGM is the high level. The second demultiplexer may also provide the address signal ADD to the second multiplexer when the first test mode signal TM PGM is the low level.

The third demultiplexer may provide the chip select signal CS  to the test pattern setup unit when the first test mode signal TM PGM is the high level. The third demultiplexer may also provide the chip select signal CS  to the third multiplexer when the first test mode signal TM PGM is the low level.

The first to third multiplexers to may output the dummy test pattern or the external test pattern as the internal command signal iCMD the internal address signal iADD and the internal chip selection signal iCS  to the memory block according to the second test mode signal TM PTN.

For example when the second test mode signal TM PTN is a high level the first to third multiplexers to may provide the dummy test pattern to the memory block .

When the second test mode signal TM PTN is a low level the first to third multiplexers to may provide the external test pattern. The external pattern may be outputs of the first to third demultiplexers to as the internal command signal iCMD the internal address signal iADD and the internal chip selection signal iCS  to the memory block .

The test pattern setup unit may store the test pattern source signal that is the command signal CMD the address signal ADD and the chip select signal CS  provided through the first to third demultiplexers to therein. The test pattern setup unit may also output the stored test pattern source signal as the dummy test pattern. In an embodiment the test pattern setup unit may be configure of a feedback loop varied according to a third test mode signal TM in which the test pattern source signal is stored. For example the test pattern setup unit may include first to third programmable pipe latches to .

The first programmable pipe latch may store the command signal CMD provided through the first demultiplexer in the feedback loop varied according to the third test mode signal TM and output the command signal CMD stored therein.

The second programmable pipe latch may store the address signal ADD provided through the second demultiplexer in the feedback loop varied according to the third test mode signal TM. The second programmable pipe latch may also output the address signal ADD stored therein.

The third programmable pipe latch may store the chip select signal CS  provided through the third demultiplexer in the feedback loop varied according to the third test mode signal TM and output the chip select signal CS  stored therein.

The first to third programmable pipe latches to may be operated in synchronization with the clock signal CLK. Further the internal storage values of the first to third programmable pipe latches to may be initialized according to the reset signal RST b.

Referring to the first programmable pipe latch may include a plurality of flip flops to and a plurality of multiplexers to .

The plurality of flip flops to may sequentially shift input signals D thereof to next stage flip flops according to the clock signal CLK.

Output values of the plurality of flip flops to may be initialized according to the reset signal RST b.

One of the plurality of multiplexers to selected according to signal bits of the third test mode signal TM may feedback an output of a previous stage flip flop to or an output of the final flip flop .

The plurality of multiplexers to may vary a length of the feedback loop that is the number of unit patterns included in the dummy test pattern according to the third test mode signal TM.

Through adjusting of the value of the third test mode signal TM the dummy test patterns of the first to fourth channels CH to CH of have the same value as each other or may have different values from each other.

For example it may be assumed that the third test mode signal TM includes 7 signal bits n 6 TM in the third test mode signal TM is a high level and TM is a low level. The first programmable pipe latch may be configured of a seven stage feedback loop for clarity loop  and generate the dummy test pattern in which 7 unit patterns are repeated.

The dummy test pattern programming may be simultaneously or selectively performed on the first to fourth channels CH to CH of .

One or a portion of the first to fourth channels CH to CH or all the first to fourth channels CH to CH may be selected using the chip select signals CS  to CS .

First it may be assumed that the first channel CH is selected by activating the chip select signal CS  and TM of the third test mode signal TM is activated.

In the dummy test pattern value of the first channel CH may be initialized by the reset signal RST b.

In a state that the first test mode signal TM PGM is set to the high level a command signal and an address signal corresponding to the command signal ADD CMD as the test pattern source signal may be sequentially input in order of NOP No Operation PCG Precharge NOP RD Read NOP WT Write and ACT Active .

Since the TM is in an activated state the dummy test pattern configured of unit patterns that is NOP PCG NOP RD NOP WT and ACT may be stored in the seven stage feedback loop Loop  formed in the first programmable pipe latch of . Accordingly the dummy test pattern programming may be completed.

When the second test mode signal TM PTN is transited to the high level the unit patterns NOP PCG NOP RD NOP WT and ACT of the dummy test pattern stored in the seven stage feedback loop Loop  may be repeatedly provided to the memory block of as the internal address signal and the internal command signal iADD iCMD.

Accordingly the first channel CH may repeatedly perform the dummy operation according to the dummy test pattern in which the seven unit patterns that is NOP PCG NOP RD NOP WT and ACT are repeated.

In another example a method of programming a dummy test pattern which is different from that of the first channel CH on the second channel CH will be described.

First it may be assumed that the second channel CH is selected by activating the chip select signal CS  and TM of the third test mode signal TM is activated.

In the dummy test pattern value of the second channel CH may be initialized by the reset signal RST b.

In a state that the first test mode signal TM PGM is set to the high level a command signal and an address signal corresponding to the command signal ADD CMD as the test pattern source signal may be sequentially input in the same order as the first channel CH that is in order of NOP PCG NOP RD NOP WT and ACT.

Since the TM is in an activated state five unit patterns that is NOP PCG NOP RD and NOP among the unit patterns NOP PCG NOP RD NOP WT and ACT of the dummy test pattern may be stored in the five stage feedback loop Loop  formed in the first programmable pipe latch of . Accordingly the dummy test pattern programming may be completed.

When the second test mode signal TM PTN is transited to the high level the unit patterns NOP PCG NOP RD and NOP of the dummy test pattern stored in the five feedback loop Loop  may be repeatedly provided to the memory block of as the internal address signal and the internal command signal iADD iCMD.

Accordingly the second channel CH may repeatedly perform the dummy operation according to the dummy test pattern in which the five unit patterns that is NOP PCG NOP RD and NOP are repeated.

Hereinafter a method of performing a test on the third channel CH among the first to fourth channels CH to CH and performing a dummy operation on the remaining channels CH CH and Ch after the dummy test pattern programming is completed will be described with reference to .

It may be assumed that the same dummy test pattern programming as that described with reference to is performed on the first channel CH and the second channel CH. Further the dummy operation timing of the fourth channel CH will be omitted in .

Since the dummy test pattern programming is completed all the first test mode signals TM PGM CH to TM PGM CH corresponding to the first to third channels CH to CH may be the low level. also illustrates the internal address signal and internal command signal iADD iCMD CH to iADD iCMD CH corresponding to the first to third channels CH to CH.

In a state that all the first test mode signals TM PGM CH to TM PGM CH are set to the low level a command signal and an address signal corresponding to the command signal ADD CMD as the external test pattern may be sequentially input in order of NOP NOP PCG NOP RD RD RD RD NOP ACT NOP PCG NOP WT NOP and ACT.

Since the first channel CH and the second channel CH perform the dummy operation the second test mode signals TM PTN CH and TM PTN CH corresponding to the first and second channels CH and CH are set to the high level. However since the third channel CH performs the normal test operation the second test mode signal TM PTN CH corresponding to the third channel CH may be set to the low level.

Accordingly the first channel CH may repeatedly perform the dummy operation according to the dummy test pattern NOP PCG NOP RD NOP WT and ACT programmed as illustrated in and simultaneously the second channel CH may repeatedly perform the dummy operation according to the dummy test pattern NOP PCG NOP RD and NOP programmed as illustrated in .

Since the second test mode signal TM PTN CH corresponding to the third channel CH is set to the low level the third channel CH may not use the previously programmed dummy test pattern. Further the third channel CH may perform the test operation according to the currently input external test pattern NOP NOP PCG NOP RD RD RD RD NOP ACT NOP PCG NOP WT NOP and ACT and perform actual data I O according to the test operation.

Since the third channel CH perform the normal test operation the dummy test pattern may be unnecessary. Further the feedback loop operations of the first to third programmable pipe latches to of the test pattern setup unit may be interrupted by setting all the signal bits of the third test mode signal TM to the low level. Accordingly current consumption may not occur.

As described above the memory system according to an embodiment may perform the dummy operation similar to the actual operation environment on the remaining channels using different dummy test patterns other than a channel which performs the normal test among the plurality of channels and thus improve the versatility and reliability of the test.

The above embodiment of the invention is illustrative and not limitative. Various alternatives and equivalents are possible. The invention is not limited by the embodiment described herein. Nor is the invention limited to any specific type of semiconductor device. Other additions subtractions or modifications are obvious in view of the invention and are intended to fall within the scope of the appended claims.

