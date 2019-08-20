### Overview
This contains a list of my local development subroutines that will extend T24 functionality

***

### Prerequisites
1. T24 TAFC R12^
1. Parameter local table created using EB.TABLE.DEFINITION (BDUH001-GEN.TABLE.xxxxxx.zip)^^
1. PGM.FILE Record for Function routine or EB.API Record for Version routine
***
### Local API

| Subroutine             | Type            | Attached on     | Description   | Input Param | Output Param | Prerequisite |
|------------------------|-----------------|-----------------|---------------|------------------|------------------|------------------|
| VR.ADD.OFS.REQUEST                  | Version Routine | BEFORE.AUTH.RTN | Add Additional OFS Request at Version Level | **This will be placed on EB.XXX.GEN.PARAM Application/Table** <br /> <br /> **ID Format** = AOR-<Version Name\>(E.g AOR-TELLER,CASH.DEPOSIT) <br /><br />**OFS Build Record ID** = Any valid application field which this routine attached, Leave as blank to generate automatic ID. <br /><br /> **OFS Build Record Version** = OFS Version  <br /><br /> **OFS Build Record Function** = OFS Function  <br /><br /> **OFS Build Record Type** = OFS type  <br /><br /> **OFS Build Record LR Type** = ADD to process after validate or INSERT to process first <br /> <br /> Kindly use *EB.XXX.GEN.PARAM,OFS.ADD.LOCAL.REQUEST* screen SETUP | Any error will being displayed on Version screen | Parameter table, EB.API Record and catalogue routine
| VR.VALIDATE.FIELDS.USING.REGEX      | Version Routine | BEFORE.AUTH.RTN | Validate fields using on REGEX Expression   | **This will be placed on EB.XXX.GEN.PARAM Application/Table** <br /> <br /> **ID Format** = <Version Name\>(E.g TELLER,CASH.DEPOSIT) <br /> <br /> **Application Name** = Valid Application <br /> <br /> **REGEX Validation** = Valid REGEX expression  <br /> <br /> **Application Fields** = Valid Application Fields <br /> <br /> **Error ID** = Valid Error ID from EB.ERROR Application  <br /> <br /> **Regex Expression Matched** = Y or N <br /><br /> Kindly use *EB.XXX.GEN.PARAM,REGEX.VALIDATION* screen SETUP | Any error will being displayed on Version screen | Parameter table, EB.API Record and catalogue routine
| BATCH.CREATE.WRITE.FILE             | Batch Function Routine   | Batch Main Routine | This will create/write file per agent. Files will be merge by BATCH.MERGE.WRITE.FILE routine | **Y.FILE.DIR** = File Directory <br /> **Y.FILENAME** = File Name <br /> **Y.FILE.EXT** = File extension <br /> **Y.RECORD** = Record || Catalogue routine
| BATCH.MERGE.WRITE.FILE              | Batch Function Routine   | .POST or .SELECT(Using Control list) Batch Routine                | This will merge files created by BATCH.CREATE.WRITE.FILE routine. | **Y.FILE.DIR** = File Directory <br /> **Y.FILENAME** = File Name <br /> **Y.TIMESTAMP** = Option to place timespamp, Set yo 'Y' |**Y.ERR** = Error | Catalogue routine
| OFS.RESPONSE.PARSER             | Batch Function Routine |  | This will extract OFS message and convert into variables | **Y.OFS.RESPONSE** = OFS Response| **Y.REC.ID** = OFS Record ID <br /> **Y.REC.STATUS** = OFS Error Message <br /> **Y.REC.STATUS.IND** = OFS Error Indicator | Catalogue routine
| GET.APP.FIELD.DET             | Function Routine |  | Return Application Field, Index, type and length | **Y.IN.APP** = Application <br /> **Y.IN.FIELD** = Field <br /> | **Y.OUT.FIELD.TYPE** = App Field type  <br /> **Y.OUT.FIELD.INDEX** = App Field index  <br /> **Y.OUT.FIELD.LEN** = App Field length <br />**Y.ERR** = Error Message | Catalogue routine


***
### Deployment Guide

1. Download the API Routine needed
1. Deploy and Catalog the routine on your BP Folder^^^

^ Might work on lower releases <br />
^^ For Version Routines only <br />
^^^ You can rename or add prefix on the routine name
