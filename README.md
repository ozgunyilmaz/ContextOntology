# Context Ontology

In this section, context ontology is described. As mentioned previously, context is modeled with context ontology encoded in OWL. By using OWL, domain ontologies are defined and shared across different platforms and people. An ontology refers to a formal representation of a set of concepts in a specific domain and the relationships between those concepts [1, 2].

Protégé [3] ontology editor is used to develop context ontology. During the development, other related work [2, 4-8] on how to develop a context ontology are taken into consideration and the best practices from these work are adopted.

The advantages of modeling the context using an ontology are providing knowledge sharing, knowledge reuse, and logical reasoning support. A general view of context ontology depicting most important classes and the relationships between them is shown in Fig. 1. Some of the classes are omitted in this figure, because there are a huge number of classes.

The context ontology is modeled through classes, object properties, data type properties and restrictions. *Entity* class represents things that can be related to a context. From Dey’s [9] definition, an entity can be a person, a place or an object. *Entity* class has four subclasses: *Person*, *Place*, *Object* and ComputationalEntity. *ComputationalEntity* has many subclasses such as *Agent*, *SmartPhone*, *MobileDevice*, *Computer* and etc.

![alt tag](/ont/doc/images/Figure.png) 
Fig. 1. A simplified view of context ontology

*Entity* is related to *Context* class. Zone, location, time, weather, social situation, device, activity, network and profile are subclasses of *Context* class. They are modeled with ontology classes for flexibility and extensibility reasons.

*Location* is composed of *Latitude*, *Longitude*, *Altitude* and *Address* classes, again for flexibility and extensibility purposes. Time spent at a place is stored in *duration* data type property. Time context consists of date, time and day of the week values. Device context includes device type, brand, model, CPU, memory, device state, battery level, last plugged time and screen resolution of the device. Network (not included in Fig. 1) context models communication costs, network type, and other quality parameters such as network bandwidth, ping, packet loss rate, error rate, throughput, latency and jitter. *Profile* class stores entity ID, description, name and etc. *PersonalProfile* and *ComputationalProfile* are derived from Profile class. *PersonalProfile* models personal information such as name, surname, age, occupation, birthdate and other demographic information, whereas *ComputationalProfile* models computational information of a computational entity. *Person* class is associated with *PersonalProfile* class. Similarly, *ComputationalEntity* is associated with *ComputationalProfile* class. Every entity must have one and only one profile which is enforced by restrictions. All of these classes can be further extended to meet other requirements.

*Weather* class represents the current weather around an entity. Weather context is acquired from a third party web service and consists of weather condition (such as sunny, cloudy, rainy, etc.), temperature, humidity, wind, and real feel temperature. Social context of the entity is composed of current mood, communication history, contacts, and nearby entities. *Movement* class models movement of the entity, and it is associated with speed, heading, state and used vehicle.

*ActionPlan* class represents the action plan (interventions) composed of sequence of actions represented by *Action* class. As a result of the rule-based-reasoning, this class is linked to the context if there is a need to interrupt the patient.

*Zone* class represents the zone, the patient is currently located in. If the patient is not located in any one of the zones including user defined zones, then it is asserted that the patient is in the neutral zone, and this fact is added into the ontology. This serves as a syntactic sugar for better expressive power.

The context ontology deals with quality of context similar to [4]. Physical sensors may produce incorrect or stale context data due to imperfect sensing and poor reliability. In the context ontology, quality is associated with a number of quality parameters, which capture different dimensions of quality. 

## References ##
[1]	T. R. Gruber, "A translation approach to portable ontology specifications," Knowledge Acquisition, vol. 5, pp. 199-220, 1993.
[2]	M. D. Rodriguez, R. F. Navarro, J. Favela, and J. Hoey, "An Ontological Representation Model to Tailor Ambient Assisted Interventions for Wandering," in AAAI Fall Symposium: Artificial Intelligence for Gerontechnology.
[3]	S. C. for Biomedical Informatics Research, "Protégé," ed, 2017.
[4]	T. Gu, X. H. Wang, H. K. Pung, and D. Q. Zhang, "An Ontology-based Context Model in Intelligent Environments," in Proceedings of Communication Networks and Distributed Systems Modeling and Simulation Conference, pp. 270-275.
[5]	R. Hervás, J. Bravo, and J. Fontecha, "A Context Model based on Ontological Languages: a Proposal for Information Visualization," Journal of Universal Computer Science, vol. 16, pp. 1539-1555, 2010.
[6]	E. C. J. Kim, "An Ontology-Based Context Model in a Smart Home," [6]	E. C. J. Kim, "An Ontology-Based Context Model in a Smart Home," M. L. Gavrilova, Gervasi Osvaldo, Kumar Vipin, Tan C. J. Kenneth, Taniar David, Laganá Antonio, Mun Youngsong, Choo Hyunseung, Ed., ed: Springer Berlin Heidelberg, 2006, pp. 11-20.
[7]	M. Mitchell, C. Meyers, A. I. A. Wang, and G. Tyson, "ContextProvider: Context awareness for medical monitoring applications," in 2011 Annual International Conference of the IEEE Engineering in Medicine and Biology Society, pp. 5244-5247.
[8]	X. H. Wang, D. Q. Zhang, T. Gu, and H. K. Pung, "Ontology based context modeling and reasoning using OWL," in Proceedings of the Second IEEE Annual Conference on Pervasive Computing and Communications Workshops, pp. 18-22.
[9]	A. K. Dey, "Understanding and Using Context," Personal and Ubiquitous Computing, vol. 5, pp. 4-7, 2001.

