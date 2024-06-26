## Edited by: Ayoub Taihi & Racim Haffaf
## Under the supervision of: M. Abdennebi

##########################################################################################################
##		                         		                                                ##
##        How to install the different softwares to simulate the LTE network (for Ubuntu Users)         ##
##	 	  		      		  	                                                ##		
##########################################################################################################

1. Install NS3 (3.35 version)

        A. Go to the following website: "https://www.nsnam.org/releases/ns-3-35/"
        B. Double-click on "ns-allinone-3.35" 
        C. A zipped directory named "ns-allinone-3.35" will be created. Unzip it
        D. Go to the directory:  "~/ns-allinone-3.35/". Then, perform the following steps: 
               a. Click on the right mouse button. Then click on "Open in Terminal"
               b. The terminal will be opened. Write the following command: "./waf configure --build-profile=optimized --enable-examples --enable-tests"
               c. Write the following command: "./waf configure --build-profile=debug --enable-examples --enable-tests"
        E. Go the following directory: "~/ns-allinone-3.35/ns-3.35/" (subdirectory of "~/ns-allione-3.35/"). Then, perform the following steps: 
               a. Click on the right mouse button. Then click on "Open in Terminal"
               b. The terminal will be opened. Write the following command: "./waf"
               c. Write the following command: "./test.py"

2. Install NetAnim (3.108 version)

        A. Go to the following directory: "~/ns-allione-3.35/netanim-3.108" (subdirectory of "~/ns-allione-3.35/") 
        B. Click on the right mouse button. Then click on "Open in Terminal"         
        C. The terminal will be opened. Write the following command: "make clean"
        D. Write the following command: "qmake NetAnim.pro"
        E. Write the following command: "make"
        F. Write the following command: "./NetAnim"

3. Simulate an LTE network 

        A. Go to the following directory: "~/ns-allinone-3.35/ns-3.35/scratch" (subdirectory of "~/ns-3.35/") 
        B. Create there a C++ file (with a ".cc" extension) for simulating the LTE network
        C. Go to the following directory: "~/ns-allinone-3.35/ns-3.35" and click on the right mouse button. Then click on "Open in Terminal" 
        D. The terminal will be opened. Write in the terminal the following command to compile the source code: "./waf --run [name_file_cc]" (the "name_file_cc" has to be written without its extension ".cc")
        E. After verifying there is no compiling error, go to the directory: "~/ns-allione-3.35/netanim-3.108/" (sub-directory of "~/ns-allione-3.35/")
        F. Click on the right mouse button. Then click on "Open in Terminal"
        G. The terminal will be opened. Run NetAnim by writing in the terminal: "./NetAnim"
        H. A NetAnim window will be opened. Click on "Open XML trace file" button located at the top of the NetAnim window
        I. Another window containing files of the directory "~/ns-allinone-3.35/ns-3.35/" will be shown. Select the XML trace file corresponding to our simulation (in our simulation it is called "lte_simulation.xml")
        J. An LTE network with different nodes will appear in the NetAnim window. Launch the simulation by clicking on "Play Animation" located at the top of the NetAnim window and watch the scenario evolution 
        K. If you want to change the nodes' characteristics (names, positions, colors...) to recognize them and to identify the role of each one based on the informations in the ".cc" file, there are basically two ways to do it: 
               a. In NetAnim (graphically)  

                       i.  Double-click on the nodes. A window showing characterics of the clicked node will appear. Click then in the characteristic you want to modify (i.e. "Node Description" to give a name for the clicked node, "Node Position" to change its position, "Node Color" to modify its color...). Modify it in the window and the changes will automatically be saved

                      ii. According to our source code describing the name and the role of each node, we gave names for them by modifying "Node Description" of each one. The nodes constituting our LTE network are defined as follows:
 
                             Node 0: Packet Gateway (PGW)

                             Node 1: Serving Gateway (SGW)

                             Node 2: Mobility Management Entity (MME)

                             Node 3: Internet

                             Nodes 4 & 5: ENodeB1 & ENodeB2 respectively

                             Nodes 6 & 7 & 8: UE1 & UE2 & UE3 respectively

                             Nodes 9 & 10 & 11: UE4 & UE5 & UE6 respectively 

                      iii. For all the nodes, we set the size (on "Node Size") to 40

                       iv. You can choose colors and positions that suit the most by combining the mix of the RGB colors (on "Node Color" on "Red", "Green" and "Blue"). In our simulation, we chose the following ones: 
           
                             PGW's color (Red, Green, Blue): (85, 91, 97). Position (Node X, Node Y): (300, 50)
 
                             SGW's color (Red, Green, Blue): (0, 170, 255). Position (Node X, Node Y): (300, 100)

                             MME's color (Red, Green, Blue): (130, 196, 108). Position (Node X, Node Y): (190, 100)

                             Internet's color (Red, Green, Blue): (255, 228, 54). Position (Node X, Node Y): (300, 10)                                       

                             ENodeB1's color (Red, Green, Blue): (255, 255, 255). Position (Node X, Node Y): (300, 200) 
 
                             ENodeB2's color (Red, Green, Blue): (255, 255, 255). Position (Node X, Node Y): (600, 200)

                             UE1's color (Red, Green, Blue): (255, 0, 0). Position (Node X, Node Y): (5, 2.5)

                             UE2's color (Red, Green, Blue): (255, 0, 0). Position (Node X, Node Y): (5, 13.25)

                             UE3's color (Red, Green, Blue): (255, 0, 0). Position (Node X, Node Y): (5, 24)

                             UE4's color (Red, Green, Blue): (0, 0, 0). Position (Node X, Node Y): (795, 32.5)

                             UE5's color (Red, Green, Blue): (0, 0, 0). Position (Node X, Node Y): (795, 43.25)

                             UE6's color (Red, Green, Blue): (0, 0, 0). Position (Node X, Node Y): (795, 54)

               b. In the ".xml" file (coding)  

                      i. Go to the following directory: "~/ns-allinone-3.35/ns-3.35/" 

                     ii. Double-click on the ".xml" file simulating the LTE network (called "lte_simulation.xml" in our simulation) and open it 
   
                    iii. The nodes' characteristics are described in the attributes of the element "node". To modify the nodes' characteristics, you have to change the value of the attributes 
   
                     iv. For instance the node "PGW" is described in the file "lte_simulation.xml" as follows: "<node id="0" sysId="0" locX="36" locY="59" />" (line 2) for the IDs and the localisation and "<nu p="c" t="0" id="0" r="255" g="0" b="0" />" (line 14) for the identification and the color. According to the modifications in "3.K.a.", the changes will be as follows: "<node id="0" sysId="0" locX="300" locY="50" />" (line2) and "<nu p="c" t="0" id="0" r="85" g="91" b="97" />" (line 14)
                 
                      v. The previous operation will be repeated for all the remaining nodes according to the modifications in "3.K.a." 

                     vi. Save results to another ".xml" file (in our simulation, it is called "lte_simulation_with_nodes_characteristics_modified.xml")

                    vii. Open the new ".xml" file in NetAnim (in the same way as in the steps from 3.E. to 3.J.)

                   viii. Repeat the "3.K.a.ii." operation to change the name of each node    

        L. Finally, visualize the packet exchange between the nodes and measure the performance of the network either by evolving them from trace files (.tr or .txt format) which are located in the directory: "~/ns-allinone-3.35/ns-3.35" using Matlab or from "pcap" files using Wireshark (in our simulation we used Matlab to measure the throughput, the delay and the packet loss and we compared them with the specifications of the 3GPP consortium which contribute to normalize the LTE network) 

## The structure of this file was inspired from the following website: "https://help.brivo.com/index.html#!openTheReadTxtFileAndFollTheInst"