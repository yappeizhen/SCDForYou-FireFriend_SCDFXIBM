## Team Name: SCDFor You 
Team Members: Yap Pei Zhen, Soh Jing Wen, Husna Alkhatib, Tan Su Yin

## Contents:
1. [Problem and Solution](#problem)
2. [Pitch Video](#video)
3. [Solution Architecture](#archi)
4. [Detailed Solution](#details)
5. [Getting Started](#start)
6. [Resources Used](#techstack)  
7. [Future Developments](#future)


### <ins>The Problem and Our Solution</ins><a name="problem"></a>
*Problem:*    


*How Technology Can Help:*  
We propose to leverage on an IoT network of existing fire-detecting sensors to collect data related to fire alarms being triggered in a cloud database. A machine learning model will then churn the data and predict the actual severity of the fire, or whether it is a false alarm. The results of data collection and analysis will then be reported through an integrated application. This application further supports the use of a voice-enabled chatbot that will answer real-time queries related to the fire event in a convenient and efficient manner.   

*Our solution:*    


### <ins>Pitch Video</ins> <a name="video"></a>
[View our pitch video]()   


### <ins>Solution Architecture</ins> <a name="archi"></a>
![Solution Architecture](https://i.ibb.co/3CTC9r9/Architecture.png)
1. AutoAI is used to generate a report regarding the status of the fire.
2. Watson Assistant chatbot uses speech to text/text to speech function to provide user real-time updates on the status of the fire.   


### <ins>Our Detailed Solution:</ins> <a name="details"></a>
[Click here](https://docs.google.com/document/d/1Xt8jDAQUd6ObM6Ji-OM-lAKlcjm6SdfbqoBJ46labT0/edit?usp=sharing)


### <ins>Getting Started</ins> <a name="start"></a>   


### <ins>Resources Used (e.g. IBM Cloudant, IBM Cloud Functions, etc...)</ins> <a name="techstack"></a>
* IBM Cloud Watson Assistant 
* IBM Cloud Node-RED
* IBM Cloud AutoAI 
* IBM Cloud Functions 

### <ins>Future Developments:</ins> <a name="future"></a>   
Since all sensors and functions are connected via IoT, they might be able to communicate with each other and activate emergency functions like water sprinklers, building alarms, or fire exit doors.  

To build on our current solution, closed-circuit television (CCTV) cameras in public spaces may also be used in predicting the risk and spread of fires. This can be done through object detection and image classification machine learning models available on IBM Cloud. Hence, image analysis can be done to determine nearby fire hazards and the structure of the premises, thereby predicting the direction, spread, and risk level of the fire. This further enables the SCDF team to plan in advance and act decisively in the face of a fire.

