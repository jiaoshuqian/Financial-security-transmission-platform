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
   ————————The outgoing Interface is encapsulated in the Interface folder, and the key negotiation program is in the SecClient and SecServer

