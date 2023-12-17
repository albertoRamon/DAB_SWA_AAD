 [[_TOC_]]
 
# How-To DAB (on SWA) using  AAD

_How-to mount DAB (Data API Builder) on SWA (Static Web Application) using AAD authentication wiht Azure Database_


### Targets / Idea:
1. Az SQL DB must be under firewall (no public IP)
2. Microsoft  DAB must use AAD authentication with Az SQL DB


![Idea architecture](pictures/pic_00.png)


### Pre-requisite I: Prepare a SWA (Static Web Application)

1. Deploy a new SWA
   Reference: [Quickstart: Build your first static web app](https://github.com/staticwebdev/vanilla-basic/generate)
   ![Pre-requistie SWA](pictures/pic_02.png)
   
2. Test connectivity 
![Test SWA connectivity](pictures/pic_01.png)

### Pre-requisite II: Prepare a Az SQL Database
1. Deploy a Az Database 

2. Be sure that is Integrated with AAD authentication

3. Be sure that is under Firewall (no public IP)

4. Test connectivity. 
   (Very important that you access througth AAD authentication, and no SQL login / password)


## How-To

### 1. How-To: Networking configuration
Because Az DB is doesn't have a public IP, we need interconnect DAB and Az DB using Private endpoints, in this case we will create both of them

### 2. How-To: Check Networking configuration (Optional)

### 3. How-To: Az DB configuration
1. We need create tables and fill some data, you can use this script from DAB GitHub

2. Grant Read permission to SWA on DB schema

### 4. How-To: DAB Configuration
1. Crate folder/config file. By default these names are fixed

2. Add DAB objects using CLI.
(You can edit the JSON file manually too, but the CLI is a good to learn and provide a propper template that you can change later)


3. Modify Connection String

4. Configure SWA / DB Connection 

5. Test Rest API


# Future
* How-to integrate AAD authentication into DAB authentication
   This manual works with public API.
   
* Other way to grant SQL Permission to AWS. 
   There are 4 conbination splits in two groups
   * Use System Management Identity (System MI)
   * Use User Management Identity (User MI)