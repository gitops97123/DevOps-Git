# Git Introduction 

Git is Distributed Revision Control and Source Code Management System with an empasis on speed. 
Git was Originaly designed and developed by **Linus Torvald** for linux kernel development. 
Git is a free software distributed under the terms of the **GNU "General Public License"** version 2. 

### Version Control System 
  
  Version Control System (VCS) is a software that helps software developers to work together and maintain a complete history of their work. 
  Revision Control System (RCS) is an independent standalone application.   


####  List below are the function of a VCS. 
  * Allow developers to work simultaneously 
  * It Stores revisions in the form of tree structures
  * It resolves conflicts during merging. if there are any updates (addition or deletion) in the same code, the RCS alerts the user regarding the same. 
  * Does not allow overwriting each other's changes
  * maintain a history of every version

####  Following are the type of VCS. 
* Centralized Version Control System (CVCs)
* Distributed / Decentralized Version Control System (DVCs)




#### Centralized Version Control System uses a central 
Server to  all files and enables team colloboration But the major drawback of CVCs is its single point of failure. i.e, failure of the central server. Unfortunetly, if the central server goes down for an hour, then during that hour, no one can collaborate at all. And even in a worst case, if the disk of the central server gets corrupted and proper backup has not been taken, then you will loose the entire history of the project. Here, DVCs comes into picture.  

#### Distributed Centralized Version Control System
Client not only check out latest snapshot of the directory but they also fully mirror the repository. if the server goes down, then the repository from any client can be copied back to the server to restore it. every checkout is a full backup of the repository Git does not rely on the central server and that is why you can perform many operations when you are offline, you can commit changes create branches, view logs, and perform other operations when you are offline, you require network connection only to publish your changes and takes the latest changes. 

#### Advantages of GIT. 
  * Free and Open Source
  * Fast and small 
  * Implicit Backup 
  * Security
  * No need of Powerfull hardware 
 
#### Reasons for implementing configuration management 

  * Avoid repudiation attack
  * Maintain project schedule
  * Deal with constantly changing market conditions
  * Deal with constantly customer requirements

#### Free and OpenSource

 Git is released under GPL's Open Source License.
 It is available freely over the internet, you can use git to manage property projects without paying a single penny. As it is in an open source you can download its source code and also perform changes accordings to your requirements.

#### Fast and Small
 As most of the operations are performed locally, it gives a huge benefit in terms of speed. Git does not rely on the central server, i.e, why, there is no need to interact with remote server for every operation. Though git mirrors entire repository, the size of the data on the client side is small. This illustrates the efficiency of Git at compressing and storing data on the client side. 

#### Implicit Backup 
 The chances of losing data are very rare when there are multiple copies of it. Data present on any client side mirrors the repository, hence it can be used in the event of a crash or disk corruption. 

#### Security
 Git uses a common cryptographic hash function called secure has function(SHA2), to name and identity objects with its database. every file and commit is check-sumed and retrived by its checksum at the time of checkout. it implies that, it is impossible to change file date, and commit message and any other data from the GIT database without knowing GIT. 

#### No need of powerful hardware
 In case, of CVCs, the central servers need to be powerful enough to serve requests of the entire team, for smaller teams.

 ![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/08.png?raw=true)
