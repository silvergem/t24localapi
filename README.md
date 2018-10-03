Welcome to <b>t24localapi</b>. This is my current local development api that extends your local development at T24 functionality

***

<b>Prerequisites</b>
1. T24 TAFC
1. Local table created using EB.TABLE.DEFINITION

***
<b>Local API </b>

| Subroutine             | Type            | Attached on     | Description                               | Parameters |
|------------------------|-----------------|-----------------|-------------------------------------------|------------|
| VR.ADD.OFS.REQUEST     | Version Routine | BEFORE.AUTH.RTN | Add Addition OFS Request at Version Level |            |
| VR.VALIDATE.FIELDS.USING.REGEX      | Version Routine | INPUT.ROUTINE   | Validate fields based on REGEX defined    |            |
|                        |                 |                 |                                           |            |

<b>Deployment Guide </b>

1. Download the API needed
1. Catalog the routine on your BP Folder

> PS 1: I.m still creating a the Table structire. Please bear with me as a do this on my free time 
