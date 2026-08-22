# EXPERIMENT 5
## ASSET-ORIENTED RISK ASSESSMENT OF STORAGE ASSETS IN AWS AND AZURE
### Objective
To identify storage assets in AWS S3 and Microsoft Azure Blob Storage, identify possible vulnerabilities and threats, and assess their likelihood, impact, and risk level.

1. Software / Cloud Services Required
•	AWS Account 
•	Microsoft Azure Account 
•	Web Browser 
•	Internet Connection
Cloud Services Used
Cloud Platform	Storage Service
AWS	Amazon S3
Microsoft Azure	Azure Blob Storage
## PART A — AWS S3 STORAGE ASSESSMENT
Step 1: Login to AWS
1.	Open the AWS Management Console. 
2.	Sign in using your AWS account. 
3.	Search for S3. 
4.	Select Amazon S3. 

Step 2: Select the S3 Bucket
1.	Click Buckets. 
2.	Select the S3 bucket created in the previous experiment. 
3.	Record: 
o	Bucket name 
o	AWS Region 
o	Number/type of objects 
<img width="1536" height="753" alt="image" src="https://github.com/user-attachments/assets/4cbc01d9-242a-460e-8d51-ae13b3ce2620" />


Step 3: Check Block Public Access
1.	Open the S3 bucket. 
2.	Select Permissions. 
3.	Locate Block public access (bucket settings). 
4.	Check Block all public access. 
Record:
•	ON → Secure configuration 
•	OFF → Potential public-access risk 
<img width="1828" height="911" alt="image" src="https://github.com/user-attachments/assets/d47c96b5-fbe7-42e7-900a-fffc608a3960" />

Step 4: Check Bucket Versioning
1.	Select the Properties tab. 
2.	Locate Bucket Versioning. 
3.	Record whether it is: 
o	Enabled 
o	Disabled 
Security purpose
Versioning helps recover previous versions of objects after accidental deletion or modification.
<img width="1593" height="688" alt="image" src="https://github.com/user-attachments/assets/52b02a6d-fb47-47d5-99b3-559050ebbb16" />


Step 5: Check Default Encryption
1.	Stay in the Properties tab. 
2.	Locate Default encryption. 
3.	Record the encryption type. 
Possible configurations include:
•	SSE-S3 
•	SSE-KMS 
•	DSSE-KMS 
Security purpose
Encryption protects stored data from unauthorized disclosure.
<img width="1501" height="382" alt="image" src="https://github.com/user-attachments/assets/14081068-73ba-457b-815a-686a244d4507" />


Step 6: Check Bucket Policy
1.	Select Permissions. 
2.	Locate Bucket policy. 
3.	Check whether a bucket policy exists. 
Record:
•	Policy exists 
•	No policy 
Note
A missing bucket policy is not automatically a vulnerability. Access may be controlled through IAM and other AWS security mechanisms.
<img width="1492" height="773" alt="image" src="https://github.com/user-attachments/assets/41e95be7-00d5-44cd-a63b-0f4f74a107d0" />


Step 7: Check Object Ownership and ACL
1.	In Permissions, locate Object Ownership. 
2.	Record the current configuration. 
A common secure configuration is:
Bucket owner enforced
This means:
•	ACLs are disabled. 
•	Objects are owned by the bucket owner. 
•	Access is controlled using policies. 
<img width="1571" height="641" alt="image" src="https://github.com/user-attachments/assets/53cc68aa-18ae-4a62-bdb5-3148431f701e" />


Step 8: Check Server Access Logging
1.	Go to Properties. 
2.	Locate Server access logging. 
3.	Record whether it is: 
o	Enabled 
o	Disabled 
Security purpose
Logging helps investigate suspicious or unauthorized access to the bucket.
<img width="1577" height="221" alt="image" src="https://github.com/user-attachments/assets/100cccb2-818e-4f86-a5eb-015595965c58" />

## PART B — AWS RISK ASSESSMENT
After checking the S3 configuration, identify possible vulnerabilities and threats.
Risk Formula
Risk Score = Likelihood × Impact
Use the following scale.
Likelihood
Score	Description
1	Very Low
2	Low
3	Medium
4	High
5	Very High
Sample AWS Risk Assessment
Students must use their actual configuration while preparing the final table.
Asset	    Vulnerability	          Threat	                                        Likelihood	Impact	Risk Score	Risk Level	Recommended Mitigation
S3 Bucket	Versioning disabled	    Accidental/malicious data deletion	             3	          4	      12	          High	    Enable versioning
S3 Bucket	Access logging disabled	Difficult investigation of unauthorized activity 3	          3	      9	            Medium	  Enable appropriate logging
S3 Bucket	Public access enabled*	Unauthorized data access	                       4	          5	      20	          Critical	Enable Block Public Access
S3 Bucket	Weak access permissions* Unauthorized modification/access	               3	          4	      12	          High	    Apply least privilege
 ## PART C — MICROSOFT AZURE BLOB STORAGE
Step 9: Login to Azure
1.	Open the Azure Portal. 
2.	Sign in using your Microsoft Azure account. 
3.	Search for Storage accounts. 
4.	Select Storage accounts. 

Step 10: Create a Storage Account
If you don't already have a Storage Account:
1.	Click Create. 
2.	Select your available Subscription. 
3.	Select or create a Resource Group. 
4.	Enter a unique Storage account name. 
5.	Select an appropriate Region. 
6.	Keep the recommended/default performance and redundancy settings unless instructed otherwise. 
7.	Review the configuration. 
8.	Click Create. 
9.	Wait until deployment is completed. 
10.	Click Go to resource. 
Screenshot: Successfully created Storage Account.
Important
Use only the resources required for this experiment and delete them later if they are no longer required, especially if the subscription can incur charges.

Step 11: Check Azure Storage Configuration
Open the newly created Storage Account.
Go to:
Settings → Configuration
Locate:
Allow Blob anonymous access
Record whether it is:
•	Enabled 
•	Disabled 
Security purpose
Anonymous access can allow users to access blob data without authentication.
For a normal secure configuration, anonymous access should generally be disabled unless specifically required.
Screenshot: Allow Blob anonymous access.

Step 12: Check Encryption
Inside the Storage Account, locate the Encryption settings.
Record:
•	Encryption status 
•	Key management configuration 
Azure Storage provides encryption at rest for stored data.
Screenshot: Encryption settings.

Step 13: Check Data Protection
Open:
Data protection
Check available options such as:
•	Blob soft delete 
•	Container soft delete 
•	Blob versioning 
•	Point-in-time recovery, where available 
Record whether the relevant protection mechanisms are enabled or disabled.
Security purpose
Data protection features help recover data after accidental deletion or modification.
Screenshot: Data Protection settings.

Step 14: Check Access Control
Go to:
Access control (IAM)
Review the assigned roles.
Look for excessive permissions such as unnecessary:
•	Owner 
•	Contributor 
•	Storage-related administrative permissions 
Security principle
Use Least Privilege:
Users should receive only the permissions required to perform their tasks.
Screenshot: Access Control (IAM).

Step 15: Check Networking
Go to:
Networking
Check how the storage account can be accessed.
Record whether access is allowed through:
•	Public networks 
•	Selected networks 
•	Private endpoints, if configured 
Security consideration
Unrestricted network access can increase the attack surface.
Screenshot: Networking configuration.

PART D — AZURE RISK ASSESSMENT
Prepare the following table using the actual configuration observed.
Asset	Vulnerability	Threat	Likelihood	Impact	Risk Score	Risk Level	Recommended Mitigation
Azure Blob Storage	Anonymous access enabled*	Unauthorized data access	4	5	20	Critical	Disable anonymous access
Azure Storage	Data protection disabled*	Permanent data loss	3	4	12	High	Enable appropriate protection
Azure Storage	Excessive permissions*	Unauthorized modification	3	4	12	High	Apply least privilege
Azure Storage	Unrestricted network access*	External attack/access	3	4	12	High	Restrict network access
PART E — COMPARISON OF AWS AND AZURE
Prepare a final comparison.
Security Control	AWS S3	Azure Blob Storage
Public access control	Block Public Access	Anonymous access control
Encryption	SSE-S3 / SSE-KMS	Azure Storage encryption
Versioning	S3 Versioning	Blob Versioning
Data recovery	Versioning / other controls	Soft Delete / Versioning
Access control	IAM / Bucket policies	RBAC / Access policies
Logging/Monitoring	S3 logging / Cloud monitoring	Azure monitoring/logging
Network security	Bucket/network controls	Storage networking / private endpoints
PART F — FINAL RISK SUMMARY
Students should summarize the identified risks.
Example:
Cloud	Asset	Major Risk	Risk Level	Mitigation
AWS	S3 Bucket	Versioning disabled	High	Enable versioning
AWS	S3 Bucket	Logging disabled	Medium	Enable appropriate logging
Azure	Blob Storage	Anonymous access*	Critical	Disable anonymous access
Azure	Blob Storage	Data protection*	High	Enable protection mechanisms
PART G — SCREENSHOTS TO SUBMIT
AWS S3
Students should capture:
1.	S3 Bucket overview 
2.	Block Public Access 
3.	Bucket Versioning 
4.	Default Encryption 
5.	Bucket Policy 
6.	Object Ownership / ACL 
7.	Server Access Logging 
Azure
Students should capture:
8.	Storage Account overview 
9.	Anonymous Blob Access 
10.	Encryption 
11.	Data Protection 
12.	Access Control (IAM) 
13.	Networking 
Final
14.	AWS Risk Assessment Table 
15.	Azure Risk Assessment Table 
16.	AWS vs Azure comparison 

RESULT
The storage assets in AWS S3 and Microsoft Azure Blob Storage were identified and analyzed. Various security configurations, vulnerabilities, threats, likelihood, and impacts were evaluated. Risk scores were calculated using the Likelihood × Impact method, and appropriate security mitigation measures were recommended.


