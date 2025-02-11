1. Introduction to secure transmission platform
  Infrastructure Platform (referred to as the Data Transmission Platform) is an infrastructure project that provides unified and standard information security services for information systems of groups and enterprises. Solve transmission security, message security, identity authentication and authentication between enterprises and point to point; It can solve the security data transmission between new cloud service nodes; It can also solve the key problems of traditional security product deployment, such as scattered, inefficient, and vulnerable systems. It is a data security transmission solution under the "logic concentration" and "business concentration" of information system.
    ————————In short: provide encryption algorithm and key for third party information system; Ensure secure communication between information systems point to point.
Complex to say: to solve the security key distribution, high concurrency cryptographic operation equipment group calls, unified encryption and decryption interface. Manage access nodes.

2. Secure transmission platform scheme
   2.1 Scheme Deployment Principles
   
   <img width="380" alt="image" src="https://github.com/user-attachments/assets/a0d4c226-20be-4190-a9ff-ffc564c9bbeb" />

   The following uses two nodes as an example to illustrate deployment:
   1) Set up an application between the head office in Beijing and N branches in Guangzhou to encrypt and decrypt data before
       communication. Beijing construction head office manages N network applications.
   2) Deploy AppInterface and SecMngKeyServer programs on the hardware servers of the Beijing branch.
   3) AppInterface and key negotiation software client (SecMngKeyClinet) are deployed on hardware servers of Guangzhou branch.
   4) Key negotiation software client software is the Win platform, linux platform program; Heterogeneous communication.
   5) Network applications are encrypted and decrypted through the AppInterface.
   
   ————————The outgoing Interface is encapsulated in the Interface folder, and the key negotiation program is in the ClientSecKey and ServerSecKey

   2.2 Scheme introduction

   <img width="415" alt="image" src="https://github.com/user-attachments/assets/0269b80e-3053-45f2-a7d5-28eefe724b44" />

   1) Third-party applications encrypt and decrypt data through the external interface.
   2) The outgoing interface searches the node key through the shared memory.
   3) The key negotiation server negotiates the key with the key negotiation client and writes the key to the shared memory. The key
             negotiation client can be an application on the linux or win platform.
   4) Key negotiation server configuration terminal (SecMngAdmin) manages access network applications to complete network lifecycle
            management; The Key Agreement Server Configuration Terminal (SecMngAdmin) can perform historical key management, audit management, and more.

   2.3 Scheme flow

    ![image](https://github.com/user-attachments/assets/0ecf8b98-8e99-4cb4-8fc2-91b037967f38)

   1) Install the database and deploy the sql script scheme of the secure transmission platform
   2) Key negotiation server configuration terminal SecMngServerAdmin, add network information, and configure background server startup
      parameters
   3) Start the background service program of Key negotiation server (SecMngServer)
   4) Start the key negotiation client program (SecMngClinet) to initiate key negotiation
   5) Third-party information system, through the external interface (AppInterface), encryption and decryption
  
   2.4 Scheme subsystem

   <img width="416" alt="image" src="https://github.com/user-attachments/assets/f0d93621-2661-4745-9049-244182ee3d2c" />

   2.5 Solution subsystem demonstration
       2.5.1 linux Platform SecMngServer and SecMngClient
           SecMngServer
   <img width="415" alt="image" src="https://github.com/user-attachments/assets/f85131a8-2673-49f6-9bfb-37c72a8d147d" />
            









