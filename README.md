## Client 
The client is run by passing in the two required arguments of the client username, 
and the hostname of the server. There are two optional arguments the first being the port,
Port: This is used to for the client to supply the port the client will connect to. If it is not 
passed in the port will default to 27993 for tcp and 27994 for tls connection. 
The s parameter is given if the client wants to use TLS connection to connect to the server. 
The main function that is run in this program is `runTCPSocket()` this method decides the 
connection type and runs the rest of the program. 

### Guessing strategy:
The client's first guess will be taken by getting a random integer, with in
the range of 0 -> the list length of the official words. 

If the server returns a retry the client then takes the marks given and filters out 
the list of possible words, by removing them with function that takes the marks array as an input. 
It then proceeds to take another random int based on the updated length of the list and make another guess.
This process is repeated until the server returns the bye message with the flag.

Once the client receives the bye message, it takes the flag and stores it in a secret_flags.txt file
and then closes the connection to the server. 


