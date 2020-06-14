## Team Name: SCDFor You 
Team Members: Yap Pei Zhen, Soh Jing Wen, Husna Alkhatib, Tan Su Yin

## Contents:
1. [Problem and Solution](#problem)
2. [Pitch Video](#video)
3. [Solution Architecture](#archi)
4. [Detailed Solution](#details)
5. [Getting Started](#start)
6. [Challenges](#challenges)
7. [Resources Used](#techstack)  
8. [Future Developments](#future)


### <ins>The Problem and Our Solution</ins><a name="problem"></a>
*__Problem:__*    
False alarms have always been a prevalent problem in the fire emergency system and response by the Singapore Civil Defence Force. When a fire alarm goes off, the security guard/fire safety manager (FSM) at the building has to go check if there is an actual fire, then report back to SCDF within 2-4 minutes.   

However, they are often unable to report back on time. As a result, the fire department will be deployed down to the scene as a precautionary measure, despite it being a false alarm. There are a few key problems when these false alarms happen.  

1. __Resources wastage__:  
Resources from the nearest fire station will be collected and prepared to be used to fight off a fire. When this happens, there might be less emergency resources as well as human resources to respond to another real emergency that may be happening at the same time.   
2. __Time wastage__:  
SCDF emergency responders will be deployed to the building where the alarm was activated, after collecting the resources necessary from the nearest fire station. This takes up time that could be used doing more productive and useful activities. There might be less time to respond to a concurrent emergency that requires more attention.  
3. __Loss in Confidence in the System__:     
According to the Fire Safety Managers’ Association Singapore, frequent false alarms may be a major hazard to the fire alarm system, as there will be a loss in confidence in the system. This may lead to them treating subsequent alarm activations as false until proven true, when it should be treated as alarm of fire until proven false. This can be seen occuring during the [Marina Bay Suites fire incident in 2014](https://www.straitstimes.com/singapore/security-guard-who-died-in-marina-bay-suites-fire-thought-alarm-was-false), which inspired our group to pursue this issue.   

The problem we have chosen to tackle is how we can create a Smart Environment to improve emergency systems. The question our team wishes to answer is: How do we make use of a network of sensors in a built environment, using Internet of Things (IoT), Predictive Technology, and Machine Learning to gain a more timely and accurate sense of emergency situations, in order to aid in early intervention?


*__How Technology Can Help:__*  
Our infrastructure is becoming “smart”. For example, sensors and Internet of Things (IoT) are being increasingly embedded in our built environment. As such, our built environment now holds a lot of useful data that can be tapped into to improve the emergency systems we have in place. Moreover, in the context of fire incidents, the use of technology increases the safety of our security guards and FSMs, as technology automatically deduces the severity of the incident without the need for them to manually go to the site to check.    

*__Our solution:__*    
Upon the triggering of any fire-detection alarms (e.g. smoke detector, heat detector) in a building, we will be leveraging an IoT network of existing fire-detecting sensors in order to collect and store sensor data in a Cloud database. A Machine Learning model will then aggregate and filter the data and perform analytics to determine whether there is a high possibility of a real fire, or whether it is a false alarm. Upon confirming a fire, the severity of the fire is analysed, and predictive technology is used to predict the direction of the fire’s spread using location data of the sensors. The results of data collection and analysis will then be reported through an application. This application will also support the use of a Voice-Enabled Chatbot that will answer real-time queries related to the fire event in a convenient and efficient manner.  


### <ins>Pitch Video</ins> <a name="video"></a>
[View our pitch video]()   


### <ins>Solution Architecture</ins> <a name="archi"></a>
![Solution Architecture](https://i.ibb.co/3CTC9r9/Architecture.png)
1. AutoAI is used to generate a report regarding the status of the fire.
2. Watson Assistant chatbot uses speech to text/text to speech function to provide user real-time updates on the status of the fire.   


### <ins>Our Detailed Solution</ins> <a name="details"></a>
[Click here](https://docs.google.com/document/d/1Xt8jDAQUd6ObM6Ji-OM-lAKlcjm6SdfbqoBJ46labT0/edit?usp=sharing)


### <ins>Getting Started</ins> <a name="start"></a>     
__Prerequisites__    
* Register for an IBM Cloud account  
* Download the code from [this GitHub repository](https://github.com/yappeizhen/SCDForYou-FireFriend_SCDFXIBM)    
* Install Node-RED locally or create a Node-RED starter application in IBM Cloud   
* Have a working project

__<ins>Creating a chatbot</ins>__
1. Create a Watson Assistant instance  
2. Click __Add Dialog skill__ to build on your assistant   
3. Click __Import skill > Choose JSON file__ and import the WatsonAssistantDialogSkill.json file 
4. Go back to the All Assistants page and open __Settings__ from the action menu 
5. Click on __API Details__ and make a note of the *Assistant ID, URL, and API Key* for future use 
6. Go back to the All Assistants page and click on the __Skills__ link, open the action menu and click __View API__ Details. Make a note of the *Skill ID* for future use  
7. Go back to your dialog skill and click on the __Preview Link__ button on the side to get a link to test your assistant. You may ask questions such as, “Where is the fire?”, and “How hot is the fire?”  

__<ins>Creating a voice-enabled FireFriend Chatbot</ins>__
1. After Node-RED is installed, add the following packages to the package.json and commit the change:
  `"Node-red-node-ui-microphone":"0.x",  
  "Node-red-dashboard":"2.x",  
  "Node-red-contrib-play-audio":"2.x"`. 
2. Import NodeRedFlow.json and __Deploy__ the flow
3. Create a Watson Speech to Text Service instance from the IBM Cloud Catalog.
    1. Click __Service credentials__
    2. Click the __View credentials__ twistie
    3. Copy the API key for future use
4. Create a Watson Text to Speech Service instance from the IBM Cloud Catalog, then follow steps 3.1 to 3.3. 
5. Open the Node-Red application URL
6. Double click the __speech to text__ node and paste the API key from the Watson Speech to Text service instance. Click __Done__.
7. Double click the __text to speech__ node and paste the API key from the Watson Text to Speech service instance. Click __Done__.
8. Double click the assistant node and paste the Skill ID into the Workspace ID field, Assistant Service Endpoint URL, and the API key from the Watson Assistant service instance. Click __Done__.
9. Click on the red __Deploy__ button
10. To view your Dashboard, go to Menu, View and select Dashboard then Click on the highlighted icon (a) to launch the dashboard
11. To talk to the chatbot, click on the microphone input button and ask a question related to the fire incident.  


__<ins>Using Auto AI to Build a Machine Learning Model</ins>__
1. Prepare the data in the dataset given
2. Add the dataset as an asset to Auto AI
3. Click __Run experiment__
4. Pick the top ranking pipeline to check model details
5. Save the model and deploy the model    

### <ins>Resources Used (e.g. IBM Cloudant, IBM Cloud Functions, etc...)</ins> <a name="techstack"></a>
* IBM Cloud Watson Assistant 
* IBM Cloud Node-RED
* IBM Cloud AutoAI 
* IBM Cloud Functions 

### <ins>Challenges</ins> <a name="challenges"></a>
Implementation of this solution requires cloud database technology to store and process massive amounts of data in real time. While this requires new expertise and investment, such technology will greatly improve the efficiency of operations and further optimise the use of precious equipment and resources in the long term.

Our implementation also relies heavily on the proper operation of fire detection sensors. Hence, such sensors will have to undergo regular checks and maintenance. However, one advantage of using integrated data from the sensors through IoT is that the database will instantly be able to detect if a sensor is malfunctioning, thus sending an alert for its repair.  

### <ins>Future Developments</ins> <a name="future"></a>   
Since all sensors and functions are connected via IoT, they might be able to communicate with each other and activate emergency functions like water sprinklers, building alarms, or fire exit doors.  

To build on our current solution, closed-circuit television (CCTV) cameras in public spaces may also be used in predicting the risk and spread of fires. This can be done through object detection and image classification machine learning models available on IBM Cloud. Hence, image analysis can be done to determine nearby fire hazards and the structure of the premises, thereby predicting the direction, spread, and risk level of the fire. This further enables the SCDF team to plan in advance and act decisively in the face of a fire.

