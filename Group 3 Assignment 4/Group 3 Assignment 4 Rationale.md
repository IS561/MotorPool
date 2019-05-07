# GROUP 3 RATIONALE AND JUSTIFICATION
Group Assignment 4 involved inference using owl. This was our task – 
Group 3: When the reasoner is active for your file, we'll see that:
•	bizactivity1 is insuredfor employeeA (because it's approved by A's supervisor)
•	bizactivity1 is an 'Insured Activity' because it's been approved by the supervisor of an employee who filled out an MVR.
•	In addition, confirm that Group 2's definitions make bizactivity1's designated driver employeeA (via the inverse).
We had to use Protégé to run the Motorpool3.owl file that was provided by the Professor. We started with the owl file. We followed part of this UML diagram to understand what needs to be done as part of the assignment. We concentrated on the highlighted classes and relationships for this assignment.

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic1.png)

For the group assignment 4, we worked together in two in-person meetings and one on-line team meetings to finish the deliverables.
In the first meeting which was online, first we discussed the requirement of the assignment. After that we identified the topics we need to understand deeper to apply in the assignment. In our first oncampus meeting as we began with the assignment first we started to re-examine the assignment outlines. We created our owl serialization file. In that we asserted "insured for" association between bizactivity1 and employeeA , and put it in instance graph. After discussion with our professor we realized that was a wrong approach. 
We understood that "insured for" edge needs to be added to the graph by Hermit reasoner, not by us. As previously done by us like the result of a datalog rule, here we are supposed to use OWL definitions instead of datalog syntax. We understood that bizactivity1 and employeeA are just instances for testing purposes. And our objective is to create a model that supports the deduction that any pair of individuals like that get the "insured for" connection for the right reason. This is because the employee travels on the business activity and because that activity is approved by the traveler's supervisor. And then in addition, if the traveler has also filled out the MVR, then the activity is an 'Insured Activity.'

We revisited professor’s lecture videos to understand what link we were missing. Then we deduced a useful generalization from the lecture video – 
	Property 1: Domain(A)  Codomain(B)
	Property 2: Domain(B)  Codomain(C)
	 Property: Domain(A)  Codomain(C)
Having seen got some idea on what to do, we first loaded the Motorpool3.owl file that professor provided on to the protégé tool. Then we could see that the object properties were populated, and the entities were not. We then populated the entities with all the relevant entities and then looked at the object properties, these were the relationships which needed domains and codomains to be associated to them as well as to their inverses. 
We also realized as given in the assignment instructions that we cannot add new individuals or properties. Also we cannot not add edges to the instance graph ourselves, which means we can't add class identities to the individuals, although we can add named or anonymous classes to the schema, relate classes to each other, relate classes to properties (via domain and range assertions), and relate properties to each other. What we essentially realized is that we are supposed to add schema level information and let the Hermit make deductions at the instance level.
After taking second feedback from our professor we realized there is an issue with the relationship 'insured on', also it was specified in the assignment that 'insured for' and 'insured on' are inverses.  We found that both bizactivity1 and employeeA are 'insured on' something, and both bizactivity1 and mvrelease1 are 'insuredfor' something. We saw that we haven't yet assigned a domain/range pair for these inverse relationships. On further analysis we realized that for correct domain/range pair the reasoner will deduce that bizactivity1 is similar as employeeA and also similar as mvrelease1 and for the model to remain logically consistent all three individuals have to be either instances of the very same class, or that their classes stand in superclass or subclass relationships with each other. We rectified our mistakes accordingly. We also modified our owl file code to say that if an employee is in an insuredon relation  with business activity it’s instance is equivalent to the instance of insured activity and hence becomes an instance of insured activity as well.
After that we realized that there is a possibility of other teams framing disjoint classes which can be in contradiction with ours. We had discussion with group 2. We asked them to confirm the definitions of their group to make bizactivity1's designated driver employeeA (via the inverse).
They confirmed the relationship employeeA driverfor bizactivity1, which means that bizactivity1 designateddriver employeeA. 

Task 1 
As we started with the first task we had to create a model that supports the deduction of "insured for" connection for the right reason: because the employee travels on the business activity and because that activity is approved by the traveler's supervisor. So, we wanted to write a chain axiom to deduce this relation – We considered the ‘approvedby’ property and the inverse of ‘supervisedby’ – ‘supervise’ to keep the arrows going in the same direction.

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic2.png)

This was the chain axiom that we wrote to deduce the “insuredfor” relationship between business activity and employee

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic3.png)

Property 1 – approvedby : Business Activity(domain) 		Supervisor(codomain)
Property 2 – supervise :      Supervisor(domain)			Employee(codomain)
 Insuredfor : Business Activity (domain) 	Employee (codomain)
Business Activity is insuredfor Employee, Inverse of this  - Employee insuredon Business Activity.
When the reasoner is active – 

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic4.png)

TASK 2
For task 2, we had to deduce that when an employee fills out an mvr, a business activity is an “insured activity”. In order to deduce this, we were not allowed to create new properties, but we could create new class. We created a new class named “Insured Activity”. We first wrongly used “insuredon” property to deduce that the business activity is an insured activity. But when we clarified with professor, he explained how this was wrong. 
Then we thought we would create insured activity class as a subclass of business activity class and also created a verified employee class as a subclass of employee class. Then we tried to get bizactivity1 as an instance of insured activity class. We were still not able to correctly get this kind of relation. We also found a problem in this approach of creating subclasses. As professor had mentioned, we had to create a model which will be in agreement with all the groups’ definitions. If we create subclasses, we felt it would create a confusion. 
Finally, we came up with a solution where we created one new class called insured activity. Instead of defining a relationship between business activity class and insured activity class, I have written an equivalent to code to say that if an employee is in an “insuredon” relation with business activity, the instance of business activity is equivalent to the instance of insured activity class and hence becomes an instance of insured activity as well. Thus, helping the Hermit reasoner deduce this. 

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic5.png)

![rule 2](https://github.com/IS561/MotorPool/blob/master/Group%203%20Assignment%204/images/pic6.png)

TASK 3
For task 3, we had to confirm with group 2 if they had made their designated driver employeeA for their bizactivity1. This we confirmed through the moodle portal open discussion forum. The group 2 confirmed that they have done the same. Hence this task was also accomplished.


	
