# Dessa2.0
Discrete Event Stochastic Simulator of Self Assembly Systems


Software Requirements


1) Java 2 Platform, Standard Edition. User can download the latest version of both JDK and JRE.

2) Java3D API: This package provides a set of object-oriented interfaces for user to build, render, and control the behavior of 3D objects and visual environments. We use this open-source library to incorporate high-quality, scalable, platform-independent 3D graphics into this Discrete Event Simulator to display the self-assembly of actin, tubulin and virus capsid visually.

*Java3D API might be pre-installed in some Linux and Mac OS platform. Windows platform does not contain this package. User should download and install Java3D API before running Dessa1.5.8 simulator.

If Linux does not contain Java3D API, user should download the package from official site. Open Terminal and locate the place where Java3D API package was extracted. Then copy the related contents to JRE folder with commands below:

sudo cp lib/ext/* /usr/lib/jvm/java-6-openjdk/jre/lib/ext/

sudo cp lib/i386/* /usr/lib/jvm/java-6-openjdk/jre/lib/i386/

Please make sure the commands match your system and JREV version.

*Eclipse users have to add Java3D API as an external library for the project. The library file can be found at the root directory of Java3D API library installed on your computer.

3) BinaryHeap.java and PriorityQueue.java. These two files in the Data Structures package, by Peter Williams, are used by our software. You do not have to download them separately, however. 

4) For Windows users, the code has been tested with Eclipse. It may not work with command-line compilation in Windows due to known issues with the required Java3D package.
Installation and Execution

*We are providing instructions for command-line use, but those using and IDE such as Eclipse should follow their IDE's instructions for compiling, setting command-line options, and executing the code. The command-line instructions are below:

1) Download "Dessa2.0.zip" and unzip it.

2) Compile the java source code inside folder "Dessa2.0" from a command line with the following command:

javac Test.java

3) Launch the program with the following command:

java Test [xmlFile.xml] [Events Per Printout][Max Simulation Time] [Random Seed] [Maximum Output Size]

For example: ccmv3_full.xml 10000 1600 4996 180

It means that the simulator will use the file ccmv3_full.xml to initiate the simulation, each line of output will correspond to 10,000 discrete events, the maximum simulation time will be 1600s, the random seed will be 4996, and each line of output will report numbers of structures of each size up to 180.

*The XML file should be placed in the same folder of your compiled java files or in another folder in your path if you have specified one.

In order to specify the maximum memory size to be allocated to the program, launch the program with the following command:

java -Xmx[Memory] Test

where [Memory] is an amount of memory to allocate. For example:

java -Xmx600m Test

will allocate a maximum of 600 megabytes memory to the program.

Standard output is a txt file named sim_ + ”input xml file name”. This file will display periodic updates of the simulation time followed by the quantity of each size of particle within the simulation. The periodicity of the data in the file is determined by the “Events per Printout” input in the simulation.


Graphical Visualization


There is an alternative execution path when specific forms of data visualization are desired. If instead of Test.java, GraphBuilder.java is used as the main file with which to compile and run the simulation, then a separate output txt file is generated called pathVec_ + ”input xml file name”. This file logs the x,y,z coordinates for every intermediate assembly along a single pathway between a single monomer and completed capsid. This data can be utilized to generate individual intermediate assembly frames or full movies of completed structures. Instructions for usage are similar to Test.java:

1) Download "Dessa2.0.zip" and unzip it.

2) Compile the java source code inside folder "Dessa2.0" from a command line with the following command:

javac GraphBuilder.java

3) Launch the program with the following command:

java GraphBuilder [xmlFile.xml] [Events Per Printout][Max Simulation Time] [Random Seed] [Maximum Output Size]

