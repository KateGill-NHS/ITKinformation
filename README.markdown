#NHS 111 Interoperability
##Usage
The purpose of this repository is for software vendors participating in the NHS 111 Programme to be able to track the development of the specifications pertinant to NHS 111 and contribute to it's success. 

It is also intended to be a issue tracker for various issues that come up through the usage of the specification in live and development environments.

By trackig it in this manner we can clearly see via diff or the diff interface the changes that have been made between versions.

Publishing sample message outputs here will allow vendors to self assure their systems with your systems prior to go live used in conjuction with the NHS ITK Testbench.

We will also collate test datasets here so we can test our systems as we learn and develop.

<Official Wording>
This is not intended to replace TRUD, it is a tool to be used without warrenty that I believe we will all benefit from using. I will only add members of organisations that have signed up to TRUD first as there are copyright implications with some of the HL7 elements.
</Official Wording>

##Structure
/ - Latest releases of core documentation with versions name removed to allow a diff

/Archive - previous specifications for quick retreival

/Sample Messages/VendorName - Sample Messages output from named vendor system to test against

/NHS111 DMS - Latest Domain Message Specification version name removed to allow a diff

##Contribute
Please fork and submit a pull request to contribute messages or code etc

Master will always represent the latest published specification and will be tagged appropriately

Issues should be created for clarification and will be answered for all to see (there are no stupid questions)

Submit pull requests to include your sample messages (we all have an easier time by signed off in a live deployment if we all contribute)

##Release Process
The official release mecanism is TRUD. I will maintain this repository and ensure multiple people have sufficient access to be able to manage it in my absense

The SME's in the messaging team will have visibility and access to reposnd to issues
