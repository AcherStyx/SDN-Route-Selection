# Visual Network Configuration of Operation and Maintenance Based on SDN
## RATIONAL
Because the traditional network management network equipment configuration is tedious, it needs to use the command line to configure one by one, manual operation will lead to the risk of operational errors; and the traditional network maintenance is difficult: the deployment of the new protocol and troubleshooting make network maintenance a very difficult task. In the SDN environment, SDN separates data from control by using the idea of hierarchy. In the control layer, including the logic centralized and programmable controller, it can master the global network information, facilitate operators and researchers to manage and configure the network and deploy new protocols. So we think about the visual network configuration and operation and maintenance in the SDN environment.


## CODE ARCHITECTURE
![总体构架](https://img-blog.csdnimg.cn/20200113124354198.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkyNDg4NQ==,size_16,color_FFFFFF,t_70)

## PPRECIATION
Work in progress. Any contribution or discussion is appreciated.

## CONTENT

- Overview of SDN Features 
  - Logical centralization
    - Logical centralization refers to the black box self-learning network equipment under the traditional network. In the SDN network environment, the separation of transfer control is realized: the control plane of the network element is on the controller, responsible for protocol calculation and generating flow tables; The forwarding plane is only on the network device. The control layer is the control center of the system, responsible for the generation of internal switching paths and border service routes of the network, and is responsible for handling network state change events.
  - Programmable
    - Directly control these hardware by compiling code to implement your own protocol or functionb. Northbound interface provides a series of rich APIs, on which developers can design their own applications without having to care about the underlying hardware details.

- Qt Programming
  - 
    - In GUI programming, when we change a control (such as a widget), we usually notify the change to another control in the UI. More generally, it is desirable for any type of object to be able to communicate with each other. For example, if the user clicks the "Close" button, we may want to call the window's close () function. The signal slot mechanism is used to communicate between two objects (two instances). The signal slot mechanism is one of the core features of Qt, and it is also the difference between Qt and other frameworks.
    - Other frameworks implement this communication using callbacks. A callback is a pointer to a function, so if you want the handler to notify you of certain events, pass the pointer to another function (callback) that handles the function. The handler then calls the callback when appropriate. Although a successful framework for using this method does exist, callbacks may not be intuitive and there may be problems in ensuring the correct type of callback parameters.
    - In Qt, there is an alternative callback technique: signals and slots. Signals when a specific event occurs. Qt's controls have many predefined signals, but you can inherit controls and add our custom signals to them. A slot is a function that is called in response to a specific signal. Qt's controls have many predefined slots, but it is common practice to inherit the controls and add custom slots so that you can handle signals of interest.
    - The signal slot mechanism is type-safe: the signature of the signal must match the signature of the slot (the signature match is the return type of the function, the parameter types match; a slot may have fewer parameters than the signal it receives, because it can ignore parameters) . Signals and slots are loosely coupled: the class that issued the signal neither knows nor cares which slot receives the signal. Qt's signal and slot mechanism ensures that if you connect a signal to a slot, the slot will be called with the signal's parameters at the appropriate time. Signals and slots can take any number of parameters of any type. They are completely type-safe.
    - All classes inherited from QObject or its subclasses (for example, QWidget) can contain signals and slots. It doesn't know or care if anything is receiving the signals it sends out, this is the real message encapsulation.Slots can be used to receive signals, but they are also ordinary member functions. Just as an object doesn't know if anything receives its signal, a slot doesn't know if it has any signal connected to it.
    - You can connect any number of signals to a single slot, or you can connect signals to any number of slots as needed. You can even connect a signal directly to another signal. (Every time the first signal is transmitted, this will immediately send the second signal.)
    
- Socket programming
  - 
    - In the field of computer communication, Socket is also called "socket". It is a protocol or a method for communication between computers. Can send data and receive data at the same time, which is equivalent to full-duplex mode in communication.There are two ways of socket communication: TCP and UDP processes. TCP is a reliable connection-oriented communication process that includes a three-way handshake and four-waves mechanism. UDP is an unreliable connectionless communication process. Clients only send it, regardless of whether the server has received it.
    
- Traffic model
  - 
    - A huge challenge in network performance evaluation is how to generate real network traffic. Programs can be used to create artificial network traffic, and a test environment can be established to simulate the real situation. This experiment takes the data center network as the target scenario to restore the real traffic situation inside the data center as much as possible in the mininet simulation environment.There are currently two commonly used traffic models: ① Random model: Host sends packets with equal probability to any other host in the network; ② Probabilistic model: In the network, host number m is probabilistic with Pt, Pa, Pc, send a data packet to the host whose host numbers are (m + i), (m + j), (m + k).We use the iperf tool in mininet to generate UDP traffic in the network. The iperf client transmits the data stream to the iperf server. The server receives and records the relevant information. Although the commands available in mininet's own console are relatively abundant, it does not provide a clear API interface to support user-defined commands. Doing some batch processing in a simulation environment such as a data center with a lot of network nodes requires a lot of work, such as generating traffic between all hosts through iperf. So we need to add custom commands to mininet and complete the expansion of new commands in mininet.
    
