# Pathways DOS DTS Endpoints #

## Proposed Endpoint Format ##

*DTSAddress*\|*InteractionID*\|*MessageType*\|*BusinessScenario*\|*WorkflowID*

- DTSAddress would be the address of the destination DTS mailbox to which the message should be sent e.g. `gpsystem123@dts.nhs.uk`

- InteractionID would be used in the same way that it is currently, and so you would only ever expect to see `urn:nhs-itk:interaction:copyRecipientNHS111CDADocument-v2-0` in this field at present. You would only ever use this if using one of the 111 CDA Message Types.

- MessageType would be one of the values from the list below - this would tell the consuming system what type of DTS .dat file should be sent to the surgery.

- BusinessScenario is the standard `Primary` or `Copy` value (you would only expect to see `Copy` really and would most likely ignore the endpoint if it had `Primary` if it had that value.

- WorkflowID would be the workflow ID to be used in the DTS control file e.g. `111_REFERRAL_COPY` or `OOH_MESSAGE`. According the DTS team, the `111_REFERRAL_COPY` workflow ID should be used for CDA messages only, and so for any other type of message, the `OOH_MESSSAGE` workflow ID should be used.

*For Primary scenario endpoints, the 5th segment would be used for the referral message, however the proposal is to use it to house the WorkflowID as referral message is not relevant to a Copy business scenario*

## Message Types ##
The proposed legacy message type values are:

**Legacy Message Types**  
EMISLV  
EMISPCS  
EMISWEB  
IPSVISION  
IPS360  
TPPSYSTMONE  
ISOFTSYNERGY  
ISOFTGANYMEDE  
MTESTEVOLUTION  
MTESTEVOLUTION  

The proposed 111 CDA message type values are:

**111 CDA Message Types**  
CDA  
PDF  
HTML

A consuming system should only process the DTS endpoint instructions for MessageTypes that they can support.

i.e. If you cannot support the proprietary format for sending DTS messages to an EMIS LV system, you would ignore this endpoint as if it were not present.




