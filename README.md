# Chord-DHT
Distributed Hash Table Implementation of Chord across multiple servers.

README

Run in each server node.
Client is command given by user in individual server’s terminal.

Compile:
javac *.java

Run :
java PeerServer BootStrap_Server_IPAddress

Functionality:

Enter join,leave command in command line to add,leave a node.
Enter insert,search along with fileName to search a file among the Chord Servers.
Enter view to view current node details.

Hash values calculated from the node ip address and file Name is used to insert node and file into the chord. Each node has node identifier and each file has file identifier.
Node can be joined only through the bootstrap server.
Bootstrap server should never be removed. Otherwise new node cannot be joined. New node can be  joined only if bootstrap server is running.
Bootstrap node can be removed.
My design is like if bootstrap node leaves, all other node should leave the chord and join again.
Insert and remove file will add the file to the respective Server in the chord.It will take the shortest route to reach the node to insert and retrieve shortest path to search from the source in terms of id space.
As and when u join a new node, its successor and predecessor will be updated.
It has a doubly linked list form of connections. Each time predecessor and successor alone is changed when a node enters or leaves the cluster.
View command prints the successor,prodecessor, fileList and current node id space of the server.
In the server from where you want to insert the file. Just place it in the directory.
File will be inserted into respective servers based on the id space which holds the file identifier inside the directory Server_ServerName_dest.
When a node leaves, all its files will be copied in its successor. and predecessor successor will be changed to current nodes successor.
Insertion and search failure handled.

