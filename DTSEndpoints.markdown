# Pathways DOS DTS Endpoints #

## Proposed Endpoint Format ##

*DTSAddress*/|*WorkflowID*/|*MessageFormat*

- DTSAddress would be the address of the destination DTS mailbox to which the message should be sent e.g. `gpsystem123@dts.nhs.uk`

- WorkflowID would be the workflow ID to be used in the DTS control file e.g. `111_REFERRAL_COPY`

- MessageFormat would inform the sending system as to which format of message can be accepted by the receiving system e.g. `EMISLV, EMISWEB`


## Workflow IDs ##

Workflow IDs are issued by the CfH DTS team. Current OOH DTS messages are sent using the `OOH_MESSAGE` workflow ID which identifies to the DTS team that the messages are part of the OOH PEM workflow.

Two new workflow IDs have been created by the DTS team to handle 111 messaging:

- `111_REFERRAL` \- to be used for primary referrals (i.e. where the service is the primary service selected from the DOS for the patient referral).
- `111_REFERRAL_COPY` \- to be used for Post Event Messaging to the patient's registered surgery.

The guidance from the DTS team is that these workflow IDs can be used however **the owner of the sending mailbox must have gained permission from the DTS team to use their mailbox for 111 traffic.**

## Message Formats ##
The proposed message format values for specific surgery systems are:

<table border=1>
	<tr>
		<th>System</th><th>MessageFormat Value</th>
	</tr>
	<tr>
		<td>EMIS LV</td><td>EMISLV</td>
	</tr>
	<tr>
		<td>EMIS PCS</td><td>EMISPCS</td>
	</tr>
	<tr>
		<td>EMIS Web</td><td>EMISWEB</td>
	</tr>
	<tr>
		<td>InPS Vision</td><td>IPSVISION</td>
	</tr>
	<tr>
		<td>InPS Vision 360</td><td>IPS360</td>
	</tr>
	<tr>
		<td>TPP SystmOne</td><td>TPPSYSTMONE</td>
	</tr>
	<tr>
		<td>Isoft Synergy</td><td>ISOFTSYNERGY</td>
	</tr>
	<tr>
		<td>Isoft Ganymede</td><td>ISOFTGANYMEDE</td>
	</tr>
	<tr>
		<td>Microtest Evolution</td><td>MTESTEVOLUTION</td>
	</tr>
	<tr>
		<td>Microtest Evolution</td><td>MTESTEVOLUTION</td>
	</tr>
</table>

The proposed generic message format values are:

<table border=1>
	<tr>
		<th>Generic Format</th><th>MessageFormat Value</th>
	</tr>
	<tr>
		<td>111 CDA Message</td><td>urn:nhs-itk:interaction:copyRecipientNHS111CDADocument-v2-0</td>
	</tr>
	<tr>
		<td>PDF</td><td>PDF</td>
	</tr>
	<tr>
		<td>HTML</td><td>HTML</td>
	</tr>
</table>

*Note: For CDA messages, the MessageFormat value should be the interactionID relating to the specific message to be sent. This then allows unique message versions to be profiled for systems based on their level of support.*

A consuming system should only process the DTS endpoint instructions for MessageFormats that they can support.

i.e. If you cannot support the proprietary format for sending DTS messages to an EMIS LV system, you would ignore this endpoint as if it were not present.


