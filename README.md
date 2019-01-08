### Overview
This contains a list of my local development subroutines that will extend T24 functionality

***

### Prerequisites
1. T24 TAFC R12
1. Local table created using EB.TABLE.DEFINITION

***
### Local API

| Subroutine             | Type            | Attached on     | Description                               | Parameters |
|------------------------|-----------------|-----------------|-------------------------------------------|------------|
| VR.ADD.OFS.REQUEST                  | Version Routine | BEFORE.AUTH.RTN | Add Additional OFS Request at Version Level |            |
| VR.VALIDATE.FIELDS.USING.REGEX      | Version Routine | INPUT.ROUTINE   | Validate fields using on REGEX Expression    |            |
|                                      |                 |                 |                                           |            |

<b>Deployment Guide </b>

1. Download the API Routine needed
1. Deploy and Catalog the routine on your BP Folder

\[1\]: It might work on lower releases 

' PS 1: I.m still creating a the Table structure. Please bear with me as I do this on my free time 

