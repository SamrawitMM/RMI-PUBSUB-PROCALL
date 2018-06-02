# RMI-PUBSUB-PROCALL

Remote Method Invocation, using java implementation
1. AddI remote interface created
2. AddC implemented remote interface AddI
3. Start rmiregistry
	i. type to the cmd the following command to start rmiregistry
	   < start rmiregistry >
4. create and start server
	 i. create server cmd, go to the RMI directory 
            If javac is not recognized, use this command 
            < set path="c:\Program Files\Java\jdk1.8.0_121\bin" >
	ii. compile all the java files using cmd 
       	    < javac *.java >
	    four java classes are going to be created
	iii. to create stub for the client , use the following command
	     < rmic AddC >
	     AddC_Stub.class will be created
	     we can not see the skeleton, because it is on the server side
	iv. to start the server use the command
	    < java Server > 
5. create and start client
	i. create client cmd, go to the RMI directory 
           If javac is not recognized, use this command 
           < set path="c:\Program Files\Java\jdk1.8.0_121\bin" >
	ii. to start the client use the command
            < java Client>
            this will result the addition of the provided inputs.



Remote Procedure Call c implementation

add.x this file specify what RPC is going to do
That is using structure, we declare arguments in
this case, two integer operands to be added latter.
Then, structure of the add.x file specifies name of 
the program using, the prefix program and the name. 
Also, the signature of the program add is specified.

using the command 
	< rpcgen -a -C add.x > 
	a - create all files
	C - create all the add.c structure files

use make command to create more files for the RPC structure
	< make -f Makefile.add >

start the server using the command
	< sudo./add_server >
	It will start listening to the clients

open another terminal for client and start the client
	< sudo ./add_client localhost >

To preview the procdure call, the code is modified,
on the add_client.c file -to have more command line arguments
so, use sudo ./add_client localhost NUM1 NUM2, while
the server is listening continuosly on localhost.

When the client requests, on the server the method called 
will be seen and the result will be returned to the client.

