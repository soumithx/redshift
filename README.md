<h1> Copying Data from s3 to Redshift </h1>
<h3> 1. Create a cluster in Redshift </h3>

<h6> a. Assign Cluster Name </h6>
<h6> b. Assign User Name and Password for your cluster </h6>
<h3> 2. Open port '5239' Port in security Group </h3>
<h5> Must be same VPC for security Group and RedShift </h5>
<h3> 3. Download JDBC Drivers for provided Cluster </h3>
<h3>   Download Sql Clients</h3>
<h6>   * SQL WorkBench is suggested . <a href="https://www.sql-workbench.eu/Workbench-Build123-Mac.tgz">Click to Download</a></h6>
<h1> Open New Profile and provide all the required Credientials to Connect redshift </h1>

<h5> Map JDBC Driver to the Driver Input Field </h5>
<h6>Provide Credientials </h6><br>
<p>User :</p> <h6> jdbc:redshift://xxxxx.cwx2s1rikfth.us-east-2.redshift.amazonaws.com:5439/xxxx</h6>
<p>Password : <p> <h6>xxxxxx</h6>


<h6> Test the connection to avoid time </h6>

<h1> Upload the files in S3 with the same region as Redshift Cluster </h1>

<h6> 1.Get Security Credientials</h6>

<h6> <h3><b>Create table with same excat columns and types ofyour data</b></h3> <p> create table registe (StartDate char(40),StartTime char(40),EndDate char(40),EndTime char(40),EventTitle char(40),AllDayEvent char(40),NoEndTime char(40),EventDescription char(40),Contact char(40),ContactEmail char(40),ContactPhone char(40),Location char(40),Category char(40),Mandatory char(40),Registration char(40),Maximum char(40),LastDateToRegister char(40));

<h3><b>Load data from s3 to Redshift using COPY command </b></h3> copy registe from 's3://xxxxx/sample.csv' DELIMITER ',' null as '\0'  credentials 'aws_access_key_id=<text>;aws_secret_access_key=<text>’ csv ACCEPTINVCHARS
 ignoreheader as 1;
<h3><b> Test the loaded Data </b></h3> select * from registe;</p></h6>


<h1> Accessing Redshift Data from Spark </h1>

<h6>Please Go through the code Which I was created in Intellij Project </h6>
<h6> <a href="https://github.com/soumithx/IdeaProjects/tree/master/Redshift"> S3 2 Redshift 2 spark 2 s3 </a> </h6>





