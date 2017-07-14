# Model Driven Software Development Project
Model Driven Software Development Project (Elite Graduate Program, Summer Term 2017). University of Augsburg / Technical University of Munich / Ludwig-Maximilian University.

**Implementation of:** Hennicker, Rolf, and Alexander Knapp. "Activity-driven synthesis of state machines." *Fundamental Approaches to Software Engineering* (2007): 87-101.

## Setup
1) Install the latest version of Eclipse Modelling Tools: https://eclipse.org/modeling/
2) Open up Eclipse and click Help->Install Modelling Components and install the following components
* Acceleo
* Operational QVT
* Sirius
* XText
* Papyrus
* OCL Tools

3) Clone the repo and import it by right clicking on your Project Explorer -> Import -> General-> Existing Projects into Workspace. Browse the SSDToStateMachine Project and import the project. Make sure that the **Copy projects into workspace is NOT checked**.
4) If your IDE cannot resolve the custom defined URIs (in our case something like *mm:...*) then right click on the project (SSDToStateMachines) -> QVT Settings -> Metamodel Settings.
Click Add and make sure the following three metamodels point to the correct .ecore files:
   * *mm:sequequencediagram* should point to **SSDToStateMachine/metamodels/sequencediagram.ecore**
   * *mm:behaviour* should point to **SSDToStateMachine/metamodels/behaviour.ecore**
   * *mm:ioautomaton* should point to **SSDToStateMachine/metamodels/ioautomaton.ecore**
   
## Running the project
In order to run the project you will need to create a run configuration. 

1) After you've imported the project, click on the Run arrow symbol in Eclipse and select Run Confirgurations
2) On the left side search for **Operational QVT Interpreter** and double click on it to create a new run configuration
3) Set the transformation module to *platform:/resource/SSDToStateMachine/transforms/0Transformation.qvto*
4) In the Transformation parameters section set the **IN Model** to *platform:/resource/SSDToStateMachine/models/atm.uml* . This file contains the two scenarios that are described in the paper.
5) In the Transformation parameters set the **OUT Model** to *platform:/resource/SSDToStateMachine/result/Transformation.uml* The generated model will be written to this file.

## Contributors
* Jan Göbel (slashburn)
* Katja Ludwig (kaulquappe23) 
* Jens Wöhrle (SweetyGott)
* Alexander Knapp (supervisor)

## Notes
* State Machine design: In each state, there is only one method in the do activity. If n actions are done in the do activity (as described in the paper cf. pp. 98), a chain of states is generated. This is an implementation detail and simplifies recursive calls. This doesn't change the state machine's behavior.
* User message (consistent with paper): An arbitrary actor (user or system actor) is sending a message to a user (in our implementation the user could also send a message to himself)
* System message (consistent with paper): An arbitrary actor (user or system actor) is sending a message to a system actor (e.g. atm, bank, consortium)
* User and system communications are distinguished by their message type (asnc -> usermessage, sync -> system message)

## Tutorials
Check out the following tutorials to learn more about QVTO:
* http://redpanda.nl/index.php?p=tutorial1
* Nolte, Siegfried. QVT-Relations Language. Springer Science & Business Media, 2009.
