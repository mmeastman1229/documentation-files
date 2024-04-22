# Reviewing and Maintaining Source Code

It is important to create and maintain a codebase for projects, and that maintenance also includes rolling back to previous versions of the code if there is an issue. IT is responsible for updating and maintaining all code used for the Grouper process. Special tools are used for the ETL process, and these tools use SQL code to extract data from source. This code is called the _**Source Extract Query (SEQ)**_. Each of the claim types has their own SEQ. Business is responsible for the logic that goes into the code, including what source fields are used to populate the SEQ and verify the changes are made.

A decision was made to use GitHub to keep the SEQ code for maintenance purposes. The role of Business is to send requirements document for code updates to IT when needed. There is currently two weekly meetings with IT and that is where requirements should be distributed. Once the changes are complete, IT will communicate to business that changes are complete and business will verify by checking GitHub for the appropriate code changes. Here are the steps to be taken:
1.  Request access to *GitHub*
2.  Request read-only access to *ETG_GROUPER_ADF_DEV* repository
3.  If code changes needed, put together requirements document and submit to IT
4.  After confirmation of changes, review changes in GitHub and signoff

## Additional information on the code and process steps will be provided below.

## Acquiring Access to GitHub and Code Repository

### Step 1: Request Access to GitHub (fake header in Word)

To obtain access to GitHub, put in a request through AccessNow. This is required to access the code repository, but will only give you access to the tool needed to view the repository, not the repository itself

### Step 2: Request Access to ETG_GROUPER_ADF_DEV repository (fake header in Word)

Once GitHub access granted, request read-only access to ETG_GROUPER_ADF_DEV repository by sending an email to SE Groupers IT. Following completion, test access by going to the repository.

## Pulling the Latest version of SEQ for Review
It is possible to utilize SQL to pull the most current SEQ. To get the individual SEQs, you will need access to enr_pub_v schema. If you currently have access, follow the steps below:

### Step 1: Open SQL Query Tool and Copy & Paste Query (fake header in Word)
Navigate to the Code section(future Link) section of this document. Find the SEQ_script (future Link) and copy and paste the code into a new editor and run the script. Depending on the script, each row returned is the SEQ for the specific claim type. 
 
Figure 10: SEQ Results for Medical Claim Types
It is important to note that the medical claim types include non-pharmacy Operational Model and Regulatory Model claim types. 
 Figure 11: Results of SEQ Query

Step 2: Extract and Clean Query
Copy and paste the cell contents into a new empty script. There will be an open quote at the very beginning of the line and a closing quote at the very end of the line. Delete both characters. The script will be on a single line and unreadable. Use whatever tool you are comfortable with to format the SQL. This is the complete code that is run in the ncap_pub_v schema to populate the input files sent to the grouper. 

## Documenting Requirements and Delivering to IT

### Put together Requirements for IT (fake header in Word)

When changes to the SEQ are required, Put a requirements document together with the changes that need to be addressed. Be sure to include the following:

-   NCAP source table name
-   ENR Target table name
-   Join to source table if not previously joined
-   Which release the code should be implemented
-   If it is an emergent release, what are the impacts to the downstream users if not implemented (i.e.  any regulatory impacts)

### Provide Requirements Document to IT (fake header in Word)
{Have discussion with Marie about this process. Fill in later}

## Testing Code Changes
Once IT confirms request is complete, run some quick tests to make sure that the code is working correctly and the output is as expected.
