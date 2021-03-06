### Initial Analysis

At start we were a bit confused about what exactly our approach to the group exercise should be and struggled a bit. So, we considered all of the object properties given by the professor and drafted a UML based on that. Later, as we started discussing more we understood that we just have to work on the Event and not on the entire case scenario. After referring to the Event Ontology document and discussing with Professor we were aable understand about how our approach should be. After that we were a bit doubtful about what our Event sub-class should be and the sub-classes related to it. Our main debate was between Bizactivity and Accident but after having a long discussion we made a unanimous decision of considering Accident as the only sub-class to Event.

### Rationale and Justification (why you choose the class/property and how you map it to the Event Ontology)
#### Classes
- Accident

We initially had several thoughts about which class should we set as subclass. We have thought about only using “Accident”, only using “BizActivity”, set both “Accident” and “BizActivity” as subclasses, and set “BizActivity” as the subclass to “Event” and “Accident” as the subclass to “BizActivity”. We first ruled out the last option since not every “BizActivity” contains an “Accident”; then we ruled out the choice of setting both classes as subclasses to “Event” as we think “BizActivity” and “Accident” are  not parallel, but “Accident” should happened during “BizActivity”. Therefore, at the end, we decided to use “Accident” as the only subclass to “Event”. 

- Employee

Based on the classes in Event Model (Raimond Y. & Abdallah S., 2007), foaf “Agent”  is the one who act actively in the event. We think only “Employee” in our defined classes has the ability to actively act in an event. Therefore, we decide to set “Employee” as the subclass to “Agent”. 

- AccidentReport

We set “AccidentReport” as the subclass to “Product” because based on Event Model (Raimond Y. & Abdallah S., 2007), “Product” is something produced during the event. We think if there is an accident, an accident report will be produced as a result of the accident. 

- Vehicle

Based on the classes in Event Model (Raimond Y. & Abdallah S., 2007), “Factor”  is typically a thing that passively been used in an event. Among the classes defined by us, we think only “Vehicle” can be a factor in an “Accident”.  


- BizActivity

Based on the classes in Event Model (Raimond Y. & Abdallah S., 2007), we set 'BizActivity' as the subclass to "TemporalEntity/Time interval". TemporalEntitiy is something that is time based. During an accident, it is essential that the accident occured during BizAcitivity (time), thus time being a critical point here.

#### Sub-event 

#### is-an: Accident(event):collision
     Collision(Sub_event)- This property provides a way to split a complex event i.e. accideny into simpler events like collision
     Domain -Accident 
     Range -collision 

#### is-an: Accident(event):roadsideassistance
     roadsideassistance(sub_event)- This property provides a way to split a complex event i.e. accident into simpler events like  roadside assisstance        
     Domain -Accident
     Range – roadsideassistance

#### Properties

#### documentedby & documents: 

Originally, we chose "reported" and "reportedby" to indicates the property between "Accident" and "AccidentReport", which conflict with Group2's decision because they are required to link "Employee" and "AccidentReport" with property "Report" and "ReportedBy". After our group posted the question on Moodel and get their reply, our group decided to change the proerpty between "Accident" and "AccidentReport" to "documents" and "documentedBy". Threfore, we solved the potential incompatibility that we original have. 

     
#### involvesdriver: Accident(Event):Employee(Agent)
     Employee(Agent) - Relates to a Employee who is involved in an accident
     Domain     - Accident
     Range      - Employee
     Inverse of - Accident:droveinaccident
     
#### involvesvehicle: Accident(Event):Vehicle(Factor)
     Vehicle(Factor) - Relates to a vehicle who is involved in an accident
     Domain     - Accident
     Range      - Vehicle
     Inverse of - Accident:vehicleinaccident

#### occuredduring: Accident(event):BizActivity(factor)
     BizActivity(Factor) - Relates to a bizactivity who is involved in an accident
     Domain     - Accident
     Range      - Bizactivity
     Inverse of - Accident:included

### Coordination with other groups ###

To make sure that our definition of classes compatible to other groups’ definitions, we posted questions on Moodle and looked over other groups’ OWL files on Github to learn how they defined their classes and avoid conflict definitions. 

**Communication with Group2**: We learned from their answer to our post that they did not define any subclasses and since they did not have a new UML so we checked their OWL file on Github to learn about class definitions. Since our group focus more on mapping the classes to the Event Ontology, we did not include as many properties between classes as Group2. For example, we did not have property between BizActivity (defined as Activity by Group 2) and Employee. However, for the common properties we have, such as “droveinaccident”, “involvesdriver” and “OccurredDuring”, our group and Group 2 did not conflict each other, the domain and range are consistent. We checked all other classes and properties in a similar way and did not find extreme difference. Therefore, we believe our definitions is compatible with Group 2’s. 

**Communication with Group3**: Similarly, we learned from Group 3’s answer on Moodle that did not define any subclass so we don’t need to worry about those, and since they also did not have a new UML, we checked their repository on Github.  Group 3 is only required to define classes and do not need to add rules of inference, so there could not be any conflicts about rules of inference and the classes. 
 
**Communication with Group5**: We directly communicated with Group 5 members and had a discussion of our schema and further about the Ontograf and OWLViz. At the start we were completely unaware but after receiving the guideline from Professor we were able to discuss with group 5 and get their insights too.Group 5 had the class accident and as we chose our event as Accident their schema helped us to understand if were using the correct properties frelated to the class.

### Any controversy/conflict which arose ###
There was some conflict when we were designing the UML diagram. All the group members had different inputs and we were not able to come to a consensus. Also, there were some conflicts as some of the members were aware of the instructions which the Professor had designed for this assignment and some were not and because of this not everyone was on the same page. One of the primary reasons for this was not having a thorough understanding of the problem statement. We were not sure about how to implement Events Ontology in Protege and link with the Motorpool file. We overcame this conflict by writing long detailed mails to the Professor asking for clairification about understanding of the problem statement. It quickly became clear that Events Ontology file has a big role to play in this assignment and all of the things we design have to be related to it. Things became simpler once the entire scope of the assignment was clear and we were able to make sense of all the requirements.

### Group Experience ### 
This assignment was quite challegening to work on as a group as we had to overcome a lot of hurdles primarily with respect to the requirements of the assignment. Since the requirements of the assignment were different from other groups, we had to look at the compatability with other groups before making decisions. We felt the problem statement was slightly complex for our group and hence the amount of efforts we had to put in together this time was far more than any other assignment we have worked on in this course. That being said, it was a thoroughly enjoyable experience to work on this group assignment as we were worked on a fairly interesting real life scenario and used Protege to model our case.

### Reference: 
Chang J., Chanthabandith D., Dutta S., Jakka P.,Liang Y.,Wang S.  *Group 3 Assignment 4*.May, 2019. Retrieved from: https://github.com/IS561/MotorPool/tree/master/Group%203%20Assignment%204

Yifei Li Y., Xiao Q., Joshi M., R.H. *Group 2 Assignment 4*. May, 2019. Retrieved from: https://github.com/IS561/MotorPool/tree/master/Group%202%20Assignment%204

Dubin D. *MotorPool3.owl* (April, 2019). Retrieved from: https://github.com/IS561/MotorPool/blob/master/MotorPool3.owl. Retrieved on May 4, 2019. 

Raimond Y. & Abdallah S. *The Event Ontology, Latest Version*. (October, 2007). Retrieved from: http://motools.sf.net/event/event.html. Retrieved on May 4, 2019.

