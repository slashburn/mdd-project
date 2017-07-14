# Model Driven Software Development Project
Model Driven Software Development Project (Elite Graduate Program, Summer Term 2017). University of Augsburg / Technical University of Munich / Ludwig-Maximilian University.

Implementation of: Hennicker, Rolf, and Alexander Knapp. "Activity-driven synthesis of state machines." Fundamental Approaches to Software Engineering (2007): 87-101.

Team members: Jan Göbel, Jens Wöhrle, Katja Ludwig

## Setup
1) Install the latest version of Eclipse Modelling Tools: https://eclipse.org/modeling/
2) Open up Eclipse and click Help->Install Modelling Components and install the following components
* Acceleo
* Operational QVT
* Sirius
* XText
* Papyrus
* OCL Tools

3) Clone the repo and import it by right clicking on your Project Explorer -> Import -> Existing Projects into Workspace. Browse the SSDToStateMachine Project and import the project.

## Tutorials
Check out the following tutorials to learn more about QVTO:
* http://redpanda.nl/index.php?p=tutorial1
* Nolte, Siegfried. QVT-Relations Language. Springer Science & Business Media, 2009.

## Notes
* State Machine design: In each state, there is only one method in the do activity. If n actions are done in the do activity (as described in the paper cf. pp. 98), a chain of states is generated. This is an implementation detail and simplifies recursive calls. This doesn't change the state machine's behavior.
* User message (consistent with paper): An arbitrary actor (user or system actor) is sending a message to a user (in our implementation the user could also send a message to himself)
* System message (consistent with paper): An arbitrary actor (user or system actor) is sending a message to a system actor (e.g. atm, bank, consortium)
* User and system communications are distinguished by their message type (asnc -> usermessage, sync -> system message)






