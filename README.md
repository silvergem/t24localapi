### Overview
This contains a list of my local development subroutines that will extend T24 functionality

***

### Prerequisites
1. T24 TAFC R12
1. Local table created using EB.TABLE.DEFINITION (BDUH001-GEN.TABLE.xxxxxx.zip)

***
### Local API

| Subroutine             | Type            | Attached on     | Description                               | Parameters |
|------------------------|-----------------|-----------------|-------------------------------------------|------------|
| VR.ADD.OFS.REQUEST                  | Version Routine | BEFORE.AUTH.RTN | Add Additional OFS Request at Version Level |            |
| VR.VALIDATE.FIELDS.USING.REGEX      | Version Routine | INPUT.ROUTINE   | Validate fields using on REGEX Expression   |            |
| BATCH.CREATE.WRITE.FILE             | Batch Routine   |                 | This will create/write file per agent. Files will be merge by BATCH.MERGE.WRITE.FILE routine |
| BATCH.MERGE.WRITE.FILE              | Batch Routine   |                 | This will merge files created by BATCH.CREATE.WRITE.FILE routine. This will be placed on .POST or .SELECT(Using Control list) file of Batch routine |

<b>Deployment Guide </b>

1. Download the API Routine needed
1. Deploy and Catalog the routine on your BP Folder

\[1\]: It might work on lower releases 

