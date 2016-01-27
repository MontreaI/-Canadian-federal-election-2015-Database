# Canadian federal election 2015 Database

## Description

SQl Server database used to store data relating to the 2015 federal election.

## Database Schema

TABLE SCHEMA

 - Province = {**provinceName**, provincePopulation, provinceGDP}

 - Riding = {**ridingName**, ridingPopulation, *provinceName*}

 - Party = {**partyID**, partyName, leaderFirstName, leaderLastName, partyWeb}

 - Ballots = {***ridingName***, **candidateFirstName**, **candidateLastName**, *partyID*,  votes}

**Bolded attributes = primary key**

*Italicized attributes = foreign attributes*

***Bolded + italicized attributes = foreign keys***

## Constraints

**THE BEHAVIOUR OF THE FOREIGN KEYS IS GIVEN BELOW:**

 - provinceName in Riding: do not allow deletion or update of referenced attributes

 - ridingName in Ballots: do not allow deletion of referenced attributes, cascade changes to referenced attributes

 - partyID in Ballots: do not allow deletion of referenced attributes, cascade changes to referenced attributes

 
**IN ADDITION TO THE FOREIGN KEY AND PRIMARY KEY CONTRAINTS WE HAVE THE FOLLOWING CONSTRAINTS:**

 - The attribute set {candidateFirstName, candidateLastName, partyID} should be specified as a candidate key in the Ballots table (no pun intended)

 - The  partyID attribute in Ballots should not be null

 - The  partyWeb attribute should be specified as a candidate key in the Party table

 - The leaderFirstName and leaderLastName attributes in the Party table should not be null

 - The votes attribute in the Ballots table should not be null, and should be greater or equal to zero

 - The sum of the votes for a riding should be less than the population of that riding

## View

** THE VIEW CONTAINS THE FOLLOWING ATTRIBUTES **

 - ridingName

 - mpFirstName (the first name of the candidate with the most votes in the riding)

 - mpLastName (the last name of the candidate with the most votes in the riding)

 - mpParty (the party name of the candidate with the most votes in the riding)

 - mpVotes (the votes cast for the candidate with the most votes in the riding)

 - totalVotes (the total number of votes cast in the riding)

## Data
