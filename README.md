# optical-networks

The purpose of the project is to introduce students to the use of the Net2Plan simulator, a
optical network modeling and design tool. Net2Plan has two tools: 
i) Offline network design modeling network topology (nodes, links, paths,protection and traffic requests) and 
ii) Traffic matrix design implementing traffic models.

Download the latest version of the simulator from here:
https://github.com/girtel/Net2Plan/releases. The program is implemented in Java and does not
requires some special installation. Just unzip the .zip file and run the file
Net2Plan.jar. The system requires Java 7 (or higher). Read the user guide
from here: http://www.net2plan.com/documentation/current/help/usersGuide.pdf, especially Chapters
1, 2 and 3 (bypassing section 3.4).

Part One:
Step 1: Implement Network Topology and Add Network Traffic.
From the menu, select Offline network design and implement the network below. All the
links must be bidirectional.
![bhma 1](https://user-images.githubusercontent.com/50678563/66704961-a50c4e80-ed29-11e9-9e08-6a774f0d2c34.png)

From the 2nd window that you open, and the View / edit network design tab, select the Network tab
and set as Link Capacity units and Demand Traffic units 'Gbps'. Select the Layer tab 0 tab and
from the tab below make the requested imports.
• Nodes tab. Set node names to n0, n1, n2, n3. Right click to add two news items
attributes at each node: "Populations" with values ​​of 1000, 1000, 5000 and 5000 Populations "with values ​​of 1000, 1000, 5000 and 5000
respectively for each node and “Populations” with values ​​of 1000, 1000, 5000 and 5000 level ”= 1 for all nodes.
• links tab. Set the capacity of all links to 100 units.
Use the option to automatically select the length of the bursts, according to
the euclidean distance between links and nodes.
• Demands tab. Add "Populations" with values ​​of 1000, 1000, 5000 and 5000 traffic "for each input-output node
routing "Populations" with 1000, 1000, 5000 and 5000 source routing values ​​". Set the load to 10 units. You notice that movement
are "Populations" with values ​​of 1000, 1000, 5000 and 5000 blocked "marked in red. This is because it does not exist yet
routing algorithm to calculate routes.
• Routes tab. Add a routing per demand route via the shortest
path based on the number of nodes. Check that you are currently running traffic (at
tab demand blocked traffic is in green).


1. Question: How many applications have been added? Show how traffic is moving for each couple
nodes (show the sequence of nodes).
Step 2: Implement Route Protection
• Routes tab. Remove all calculated routes and recalculate
these using 1 + 1 link protection with “Populations” values ​​of 1000, 1000, 5000 and 5000 link disjoint path ”, minimizing the
number of hops.
2. Question: Show for each request / move which is the primary and most backup path.

Step 3: Implement hop-by hop IP routing
• Routes tab. Remove all calculated routes
• Demands tab. Change traffic from "Populations" to 1000, 1000, 5000 and 5000 source-routing "to" Populations "to 1000, 1000, 5000 and 5000 hop-by-hop". Applications
is blocked because no routing routes have been calculated.
• Forwading rules tab. Add forward rules from each node to each
node. Select automatic calculation with “Populations” with 1000, 1000, 5000 and 5000 ECMP forwarding rules from IGP link
weights ”. This option creates the rules for forwarding packets to each node
as a typical IP network that implements the OSPF algorithm. Check that traffic
it is routed (Demands tab).
3. Question: For each node, indicate the traffic paths.

Step 4: Implement multicast on IP networks.
Forwading tab: Remove all routing rules that have been calculated.
Multicast demands tab: Add a "Populations" with values ​​of 1000, 1000, 5000 and 5000 broadcast "request source each node
network. Set the traffic of each multicast request equal to 0.5 units. See that the applications are
blocked because you require the calculation of "Populations" routing routes with values ​​of 1000, 1000, 5000 and 5000 multicast trees. "
Question: How many applications were calculated in total?
Multicast trees tab: Select the route calculation using mulitcast-trees
minimize the average value of the links you use for each request. Check that all
applications are now being routed.
4. Question: show the calculated routes for each multicast request.
Step 5: Implement Route / Node Group Protection on IP Networks.
The protection of a group of paths and nodes is intended to protect them when from
these fail at the same time. You require the creation of a group
shared-risk group (SRG) that will be protected simultaneously.
Shared-risk groups tab: Select the SRGs for each bidirectional link. (each
bidirectional linking is a group that one way if its off
traffic will automatically go out the other). Select for each link that goes out
operating once every 8760 hours (once a year, MTTF parameter) and needed by
Average 12 hours to repair (MTTR parameter)
5. Question: How many protection groups have been created?

Step 6: Aggregated Network Elements.
Layer tab. You can see aggregated data such as the number of network nodes,
number of links, requests / traffic etc. Selecting the general tab
Question: What is the average of hops, distance and latency in the network? Which n
price of “Populations” with 1000, 1000, 5000 and 5000 network congestion values ​​”?
6. Question: What should be the capacity of the links for the value of the network?
congestion to become “Populations” with values ​​of 1000, 1000, 5000 and 5000 1 ”?


Part 2:
Step 1: From the tab “Populations” with values ​​of 1000, 1000, 5000 and 5000 Offline Algorithms ”select the algorithm
'Offline_ipOverWdm_routingSpectrumAndModulationAssignmentHeuristicNotGrooming
(com.net2lan.exampes.general.offline).
