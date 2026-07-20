
**Scrap Sheet:**

1. Get Uplod Credentials

returns S3 cred

2. //// Call S3 APIs directly to upload the file

3. Get files overview

shows the user

1 file identified as SoV (or more)

2 files identified as Slips (select priority for slips)

4. Create RDR process (session)

Req: folderId, priority of slips

Res: sessionId

  
  

Processing of Slip --> pipeline 1

Processing of SoV --> pipeline 2

  

a json object for account with 100 locs and 5 policies and 10 pol codnitions, coverages.......

  

4.1. GET session status

returns session status

5. Review

  

6. Import Job (IRP) --> folderId

--> importType: ExposureBatch

--> resourceUri: /platform/riskdata/v1/exposures/121231

--> settings:

--> sessionId: 53542

--> importType: ExposureBatch

-------------------------------------------------------------------------------------------------