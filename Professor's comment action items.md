I'm pleased with the teamwork you demonstrated. For future group assignments, please consider using more of Github's flexible and powerful progress tracking and version management. All of you could be updating the repository asynchronously.  10 points for teamwork, though. - **WIP**

There are some spelling mistakes you missed. Moving forward you'll want to correct those. **Done - corected previous files**

Comments on the modeling choices:

1) It sounds from your description like there is only one University of Kentucky Administration Department. In that case, why model it as a entity class if there's only one instance? - **Can do 2 things, remove this or make it generic (just university), what do you guys think?**

2) Same issue with UK Risk Management. - **Same as above**

3) It seems strange that driver would be an attribute of Motor Vehicle if the vehicle is driven by different drivers at different times. **Yeah! I am not sure how to model this, will think and update, lets discuss** 

4) How is the sex of the driver important for monitoring policy conformance? **This is not important for monitoring policy conformance, but it identifies the driver - so as a driver attribute/identifier it might be necessary**

5) Is there only one Driver Safety Awareness Training Course Test? If so, it seems strange to model it as an entity class. **Just one is listed right?**

6) You have "drives" with a 1-to-1 cardinality. It seems reasonable that vehicle would only be driven by one driver at a time, but over a period of time of interest to a policy review the same vehicle would be driven by different drivers, and a single driver might drive more than one vehicle. The 1-to-1 cardinality only seems to help keep track of who has the vehicle today, but unhelpful for knowing who was driving it when an accident took place. **That is correct, Over all it will be many to many but to connect the accident to the driver we need one to one mapping tied to the date maybe. What do you guys think? can we have a combined attribute - date+driver??**

7) I see the usefulness of the "shares information" relationship, but if either the domain or codomain are classes with only one instance, I'd urge you to consider rethinking what kinds of things participate in the relationship. Consider the information itself as a possible participant. **If we do not specify the university name, this will still hold good. However as professor suggested can we make information as possible participant? I need to think more on this**

8) If the training test result is part of the experience of the safety course, then consider either bringing the training result into the training test entity or else making "takes" a ternary instead of a binary relationship.

9) The "approves" relation may also need a different arity or cardinality, since the same administrator might approve the same driver for different vehicle uses at different times
