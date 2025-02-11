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

   SecMngClient

   <img width="416" alt="image" src="https://github.com/user-attachments/assets/ca56d31b-e8c1-4cbf-960d-3032c9c6a763" />

      2.5.2 Win Platform SecMngServerAdmin

   <img width="416" alt="image" src="https://github.com/user-attachments/assets/1a85a8ee-929f-4a7e-b2e9-d627fab664d6" />

   <img width="415" alt="image" src="https://github.com/user-attachments/assets/31617bfe-a8da-4fa5-9348-76ba5c9b0547" />


    2.5.3 Linux Basic component

   <img width="415" alt="image" src="https://github.com/user-attachments/assets/ae38aa92-19b5-495d-a8f0-0dbcc041bac9" />

    2.5.4 Win Basic Component
   
   <img width="331" alt="image" src="https://github.com/user-attachments/assets/fcc7c66f-e708-4aff-89f2-1afb5499a649" />

   
3. Process for deploying the secure transmission platform
   3.1 Deploy database solutions for secure transport platforms
       1）In Windows, use the oracle Enterprise Manger Consol tool on the oracle client to connect to the oracle database in linux

   <img width="415" alt="image" src="https://github.com/user-attachments/assets/cb71b1cd-48c5-445f-9a84-ce42ab0488a0" />


   3.2 Deploy the SecMngServerAdmin management control terminal
     3.2.1 ODBC Database configuration
       3.2.1.1 Configure the terminal network service name
         The management terminal uses the ODBC mechanism to connect to the oracle database. Before connecting to the system database, configure the ORACLE network service name.
          1. Run "Net Configuration Assistant"

<img width="478" alt="image" src="https://github.com/user-attachments/assets/c9f6e908-43c3-4be9-87e0-9dd6e1b7dcc2" />
         
          
  2. Select Local Network Service Name Configuration.

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/885dca53-9f06-4880-bec6-6539a818cb81" />

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/17b547a3-5ef4-4a2c-a813-e7dd873ff503" />

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/e61750e1-8cec-4c89-846a-14d4c827e8c4" />

  <img width="396" alt="image" src="https://github.com/user-attachments/assets/0d49e513-e469-44fb-958e-c4714f53693c" />

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/0405b1a4-567e-4665-95c4-1daaae65440f" />


  <img width="415" alt="image" src="https://github.com/user-attachments/assets/d052e7ae-1588-4158-b1c2-8151feb4ec5e" />

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/a4c84516-be52-4271-b758-24cde0a11baa" />

  <img width="415" alt="image" src="https://github.com/user-attachments/assets/89b41efc-76fa-47eb-bf96-29c61abe5c89" />

      
      
  3.2.1.2 ODBC Environment Configuration of the system Terminal

  1. select "Control Panel" -&gt; "Management Tools" -&gt; Data Source (ODBC), select the System DSN TAB.
  2. Select "Oracle in OraHome90" and click "Finish"
  3. Enter the data source name (user-defined), select the service name, and fill in the database user name
  4. Select Test Connection to test the database connection

     <img width="325" alt="image" src="https://github.com/user-attachments/assets/70b974fc-7721-4407-8ac7-0144038231a9" />

     <img width="352" alt="image" src="https://github.com/user-attachments/assets/f4fb1707-95be-4453-8631-2cbee93c5143" />

     <img width="326" alt="image" src="https://github.com/user-attachments/assets/aa45a6b8-2c1d-4f29-8980-7ce07f58335b" />

     <img width="195" alt="image" src="https://github.com/user-attachments/assets/66dfb89c-852b-4d39-85f1-8a354a8de47b" />

     <img width="121" alt="image" src="https://github.com/user-attachments/assets/8d8049ff-5acd-4ed1-8410-1c5da553edc0" />


  3.2.2 Managing the Terminal Using SecMngServerAdmin

  3.2.3 Deploying the SecMngServer
  
  Example Create user user01
  Uploading a tar Package
  Configure user environment variables
  Test database environment
  Note: For this application, serverid 0001 clientid1111 is the default
  Startup server
  Shut down the server
  View the system shared memory

  3.2.4 Deploying the SecMngClient
  
  3.2.4.1 Deploying SecMngClient in Windows
  
  Guarantee win host and linux server network normally
  
  3.2.4.2 Deploying the SecMngClient in linux
  
  Guarantee win host and linux server network normally
  
  3.2.5 Deploying External Ports
  
  Example Create user user02
  Uploading a tar Package
  Configure user environment variables
  Test database environment
  Note: For this application, serverid 0001 clientid1111 is the default
  Testing the outgoing interface
  View the system shared memory







   










