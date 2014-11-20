docker-freelan-supernode
========================

The base docker image that will be used by the more tech savy users who have on open port on a public static ip.

This node will have an initialise script which will do the following:
 
 * Uses environmental variable for location of certificate authority (ca)
 * Create certificate and send it off for signing accompanied by ca defined auto-sign network password (also environmental variable)
 * Request access to collaborate on git repository which allows the documentation of the static ips and ports of supernodes on the network along with the privliged nodes
   * uses environmental variable for the location of this git -- makes it so the image can be initialised with a one liner
 * Creates the freelan config file based on the other available supernodes
 * creates ssh keys, sets up ssh server

User will then save this initialised docker image locally

Periodically will
 * Do a git pull in case more supernodes or privliged users have been added
 * Update freelan config file with new supernodes
 * Do key swap with all of the not before seen priviliged nodes for no-password ssh (so the privliged nodes can run IPython engines)

