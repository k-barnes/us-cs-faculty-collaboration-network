# us-cs-faculty-collaboration-network

Supplementary data for the paper "Edge interventions can mitigate demographic and prestige disparities in the Computer Science coauthorship network" (2025). The data was hand-collected in 2024-25 according to the procedure described in our paper.

The data consist of a census of 5,670 computer science faculty at Ph.D. granting institutions in the US, including the following features:

|    feature     | type  | values taken | description |
| -------------- | ----- | -------- | ----- |
| Name   | string | -    | copied from CS department faculty websites |
| Dblp ID | string   | -     | publishing name as indexed by DBLP |
| CurrentInstitution       | string   | -      | 178 unique institutions |
| Email         | string | -    | copied from CS department faculty websites |
| PhDInstitution         | string | -    | 800 unique institutions |
| Title         | categorical | Professor, Associate Professor, Assistant Professor, Distinguished Professor   | professor rank |
| Named position        | binary | yes, no   | professor rank |
| Perceived gender      | categorical | Man, Woman, Non-binary or unsure, No photo found   | gender perceived by coders |
| Perceived race      | categorical | White, East Asian, Southeast Asian, Indian / Indian subcontinent, Middle Eastern / North African, Black, Latinx, Multiracial or Unsure, No photo found, Native Hawaiian or Pacific Islander   | race perceived by coders according to U.S. census categories |
| Pronous     | categorical | he/him, no pronouns found, she/her, they/them, he/them or they/he, neo pronouns or other, she/them or they/she  | recorded as part of the coding procedure |
| inferredGender-GenderGuesser   | categorical | unknown, andy, male, female, mostly_male, mostly_female   | GenderGuesser name-based inference label |
| inferredGender-NamsorFullName  | dictionary | -   | NamsorFullName name-based inference label and probability |
| inferredGender-NonQuamGender  | dictionary | -   | NonQuamGender name-based inference label and probability |
| inferredGender-WikiGendersort  | categorical | INI, F, UNI, UNK, M  | WikiGendersort name-based inference label |
| inferredEthnicity-Ethnea  | dictionary | -   | Ethnea name-based inference label and probability |
| inferredEthnicity-EthnicolrCensus  | dictionary | -   | EthnicolrCensus name-based inference label and probability |
| inferredEthnicity-EthnicolrFlorida  | dictionary | -   | EthnicolrFlorida name-based inference label and probability |
| inferredEthnicity-EthnicolrWiki  | dictionary | -   | EthnicolrWiki name-based inference label and probability |
| inferredEthnicity-Ethnicseer  | categorical | ger, chi, ind, spa, eng, frn, ita, rus, mea, kor, jap, vie | Ethnicseer name-based inference label |
| homepage  | string | -   | copied from CS department faculty websites |
| node_id  | integer | -   | unique ID linking faculty metadata with edge list |
| InstitutionId  | integer | -   | unique ID linking CurrentInstitution to prestige rankings |
| PhD_InstitutionId  | integer | -   | unique ID linking PhDInstitution to prestige rankings |
| combined_gender_estimate  | categorical | Man, Woman, Non-binary or unsure, No photo found  | gender meta-label algirithmically estimated to maximize alignment with survey self-identification |
| combined_race_estimate  | categorical | White, East Asian, Southeast Asian, Indian / Indian subcontinent, Middle Eastern / North African, Black, Latinx, Multiracial or Unsure, No photo found, Native Hawaiian or Pacific Islander  | race meta-label algirithmically estimated to maximize alignment with survey self-identification |

The node metadata given above is linked to an edge list for a coauthorship network built from 3,652,370 journal articles and 3,563,465 conference proceedings indexed by the DBLP Computer Science Bibliography:

|      feature       |  type | description |
| -------------- | ----- | -------- | 
| src   | string | faculty names   | 
| trg | string   | faculty names     | 
| years      | dictionary   | faculty number of coauthored publications per year   | 
| weight     | integer | total number of coauthored publications  | 
| src_id    | integer | links to node_id in faculty metadata file  | 
| trg_id    | integer | links to node_id in faculty metadata file   | 
