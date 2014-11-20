docker-freelan-supernode
========================

The base docker image that will be used by the more tech savy users who have on open port on a public static ip.

This node will have an initialise script which will do the following:
 
 * Request user for location of certificate authority (ca)
 * Create certificate and send it off for signing accompanied by ca defined auto-sign network password
 * Request access to collaborate on git repository which allows the documentation of the static ips and ports of supernodes on the network along with the privliged nodes -- requests user for the location of this git
 * Creates the freelan config file based on the other available supernodes (will do a git pull on boot in case more supernodes have been added)
 * creates ssh keys, sets up ssh server

User will then save this initialised docker image locally

Periodically will
 * Do key swap with all of the not before seen priviliged nodes for no-password ssh (so the privliged nodes can run IPython engines)
