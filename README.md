### About CDL
CivicDataLab works with a goal to use data, tech, design and social science to strengthen the course of civic engagements. We work to harness the potential of open-source movement to enable citizens to engage better with public reforms. We aim to grow data and tech literacy of various governments, nonprofits, think-tanks, media houses, universities etc to enable data-driven decision making at scale. The team has been instrumental in starting initiatives like DataKind Bangalore, Open Budgets India, etc. We believe in becoming thought partners in change with the help of our collaborations.

### Purpose of the publication
The Open Contracting Data Standard (OCDS) enables organisations to publish contracting process information at all the stages. OCDS defines a standard data model for  publishing contracting process data and documents with the aim of improving transparency and consumability of governmental data
Himachal Pradesh publishes its contracting process information on https://hptenders.gov.in/nicgep/app. This portal provides all information on purchases done by districts of himachal in an open format. However, the data published is not in a consumable format and is behind captchas. Therefore the importance of implementing OCDS are following

* Promote the transparency in decision making
* Provide data in machine readable formats
* Increase consumption of contracting data across the globe
* Provide ample amount of metadata to understand the contracting data

### OCDS Dataset Creation
Himachal Pradesh Finance Department publishes purchase and contracting related data on https://hptenders.gov.in/nicgep/app. This portal includes two stage data tender and awards divided into different categories like tenders in archive, results of tender, tenders by organisation. However to start with we extracted awards data from https://eprocure.gov.in/mmp/index which is a national level e-governance platform. After extracting the awards data we boiled down the tenders to health and water related tenders. We used these tender ids to get the other tender related information like buyer name, published tender value etc from tenders in archive section of  https://hptenders.gov.in/nicgep/app

* The data published in this platform is in open format behind a captcha and the data is published using html tables. We used Scrapy Python’s library for scraping and Python scripts to bring it to OCDS data models.
* Few caveats faced while converting the data were:
* There was not enough metadata published on hp tenders to understand the data
* Automating Captcha cracking to collect each data from hp tenders added an additional step 
* Data from national e-governance platform and hp tenders, in some cases wont match 
There was no clear demarcation of lots, there are few ids where only the last digit would change. For example when you search  2019_PWD_26098_1 tender id in hp tender’s tender in the archive section you will get 8 different tenders with last digit changed like 2019_PWD_26098_15. But they couldn't qualify as lots.

### Publication Policy
This document consist of following sections
* Purpose of the publication
* OCDS Dataset Creation
* Tender: Gives detailed description of fields of tender stage for contracting data
* Award: Gives detailed description of fields of award stage for contracting data
* Extensions
* License
Please find link to document [here](https://docs.google.com/document/d/1UBL1Oe3JtrVFd65Df6NzeDI_Qsh5xpwY51DVK1YImG4/edit?usp=sharing)
