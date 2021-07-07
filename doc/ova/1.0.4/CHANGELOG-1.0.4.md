# CORTX OVA 1.0.4

This release notes  includes new features and bug fixes added to the CORTX OVA 1.0.4. 

# Features:

 - The serial number displays on the About page.
 - The hostname displays on the UI.
 - Added the FRU level while generating the support bundle.
 - Created an ISO bundle to allow deployment in the isolated environment.
 - Passwords are generating dynamically during the deployment.
 - Prevented the duplication of the cluster_ids to avoid double encryption.
 - Integrated the LDAP configuration scripts with the Provisioner.
 - Added the S3 Services through CA-signed certificates on EES.
 - Updated the ADDB logs path in the var/motr/s3server directory.
 - Updated the S3 Working directory to /var/log/seagate/motr.
 - Removed the access of the S3 account to create CSM users from the backend.
 - Encrypted the passwords saved in the /etc/csm/csm.conf files.
 - Only the S3 account user can delete the buckets from their account using CSM-CLI.
 - A CSM user with a monitor role can view the list of available commands for which the user has access using the help (-h) command.
 - A user can un-acknowledge an alert using the rest request.
 - Updated the disk usage alert generation, APIs, and test cases.
 - Users can start a node resource using the system start [resource_name] command.
 - Debug level logs are available for all the implemented components after the successful installation.
 - Info level logs are available for all the implemented components after the configuration.
 - Root users can use CSM-CLI to change other user passwords and roles by specifying old_password.
 - CSM users with monitor roles cannot perform list, update, delete, and create operations on iam_users using the CSM-CLI.
 - Implemented the dynamic password fetching for LDAP and RAS.
 - A CSM user with a role manager cannot perform any REST API request on an IAM user.
 - Configure the Dev hardware client to test the DI automated test.
 - API response of audit logs for the S3 component contains the specified parameters information in the specified format.
 - Log-in error message is not displaying any confidential information.
 - A non-root user cannot change its password by specifying old_password and password through CSM-CLI.
 - Print the Motr ret code in the S3 log file for easier debugging.
 - Updated the netty jar in the AUTH server.
 - Provided the metadata extraction script.
 - The rest request with default arguments returns appropriate records.
 - Added the support for put-copy-object.
 - The bucket policy denying access to S3 IAM users when allows permission present.
 - Bucket policy allows access when both deny and allow permission is present.
 - Added the Serial Number generated during the manufacturing process in the manifest support bundle.
 - The code refactoring to the Motr wrapper file to have member functions defined in a separate C++ file.
 - The GET API returns with 400 response code if the value of from param is greater than the value of to param.
 - For no param interval and total_sample in the request, the GET API returns with 200 as a response code and appropriate with JSON response.

# Bug Fixes:

- Added the prerequisite requirement for Node replacement.
- Fixed the STONITH issue.
- Fixed the issue of the SAS HBA Alerts (Fault/Fault resolved) that goes missing after component replacement SAS HBA.
- Fixed the issue of the cluster going into the unusable state when Node 2 is powering off.
- Updated all the health resources.
- Updated the StatsD plug-in.
- Updated the CSM setup to fix the CSM configuration issues.
- Fixed the file naming convention issue.
- Updated the path to collect the motr logs.
- Fixed the tar file creation issue. 
- Updated the cron timeout to fix the system shutdown issue. 
- Fixed the time-zone issue.
- Fixed the issue of private network fault alert on UI.
- The Capacity details are displaying in the CSM GUI. 
- Fixed the issue of deployment is failed on the Intel servers.
- After the UDS RPMs are installed the UDS service file will be updated.
- Fixed the issue of salt-minion is in failed state on a primary node after the software update.
- Fixed the issue of Health map for node-1 and Enclosure went missing when Node-1 is in standby mode. 
- Fixed the issue of the Kernel Mismatch error on the CentOS 7.8 cluster setup. 
- Fixed the issue of the Health view page is displaying the old hostname.
- Fixed the issue of deployment is failing due to the cryptography python package absent. 
- Fixed the issue when the SSPL installation is getting failed with requisites were not found an error. 
- Fixed the issue of deploy replacement is getting failed as the serial number is already assigned in stage 1. 
- Fixed the issue of cortxub user password is not expiring at the first login. 
- Fixed the issue of the CSM UI giving a success message for a software update when the software update is failed using CSM UI. 
- Fixed the issue of the beta build deployment fails on the dell systems as the mpath fails to set different priorities on LUNs. 
- Fixed the issue of the cortxub user's first login with credentials failed with permission denied. 
- Fixed the issue when the unboxing fails with ERROR - Salt client command failed and static network configuration. 
- Fixed the issue where the unboxing script fails to update the SSH file. 
- Fixed the issue where post successful build deployment, the stonith resource is missing in PCS status as BMC IP for primary node failed to update in the cluster pillar file. 
- Fixed the issue of the primary node is inaccessible from the secondary node and PCS status shows all services up. 
- Moved the cluster out of maintenance state after the CSM config stage. 
- Fixed the issue of the Node replacement failed in deploy replacement stage 2 for the NodeJS after boxing-unboxing. 
- Fixed the issue of unboxing with the static network configuration. 
- Fixed the issue where the NodeJS installation fails during the node replacement due to missing entries in the "salt-call pillar.items commons". 
- Fixed the issue of the unboxing is hung while updating management VIP in the pillar. 
- Updated the HA Proxy for the DHCP environment. 
- Fixed the issue where the IP validation fails for the public data network. 
- Blocked the Motr remote access on the management and data networks. 
- Fixed the issue of unboxing fails when hostname and IP are changed during unboxing at the volume creation phase. 
- Fixed the issue of the VIPs failed to update while unboxing in the DHCP environment.
- Generating the support bundle for the current state of system health view dynamically. 
- Fixed the consul error for HCTL Status. 
- Added the alerts for the FAN insertion and removal. 
- Fixed the PC cluster stop command issue for Node reboot. 
- Fixed the deployment for 1TB, 3TB, and 5TB volume size. 
- Fixed the Node replacement issue. 
- Fixed the CSM GUI update issue. 
- Fixed the issue of unboxing failure. 
- Fixed the issue of the HA installation caused the deployment to fail due to consul_watcher. Also, removed the VM-related configuration. 
- Changed the owner of the SSPL directory to the sspl-ll user to access the "/var/cortx/sspl" directory in SSPL code. 
- Added the lshw package as a required package in sspl-ll.spec file. 
- Fixed the issue that was causing multiple "RAID integrity" alerts generation. 
- Updated the resource health view script to add a node disk dictionary in the node data OS section. 
- Added the change to retry consul if there is an internal server error and to store the message in consul if there is any type of error happens while publishing the message to the RabbitMQ Queue.
- Updated the SSPL resource stop logic. 
- Stored minion ID, consul host, and port in conf file during sspl_config, to start SSPL service in minimum time on a replaced node after node replacement. 
- Used the show configuration API to fetch the correct chassis serial number. 
- Fixed the Invalid Session key handle error.
- Updated the JSON messages. 
- Updated the pyinstaller version. 
- Added the cortx-prvsnr installation as part of the cortx-csm build process. 
- Removed the uninstalled packages from the CORTX component list. 
- Improve the performance of the S3 Server. 
- Fixed the issue of illegal characters generated as part of the S3 access key. 
- Fix the S3 sanity cleanup issues. 
- Fixed the issue where the NextMarker is not getting properly set in list-objects using boto3 when the bucket contains more than 1000 objects. 
- Fixed the issue where object listing with prefix specified continues key enumeration even after prefix match stops. 
- Fixed the bucket policy allows access when both deny and allow permission is present. 
- The s3_bundle_generate.sh script displays the error "Repository 'csm_uploads': Error parsing config: Error parsing "baseurl = '/3rd_party'": URL must be http, ftp, file or https not ""
- Fixed the issue of handle probable delete index entry delete while s3server failure during object writes.
- Added the fsync call to the put_keyval operation.
- CSM CLI/GUI list 500 users.
- [Splunk] Fixed the Ceph S3 regression in list object API. 
- [Splunk] Fixed the issue of failure for s3tests.functional.test_s3.test_bucket_acls_changes_persistent. 
- [Splunk] Fixed the issue of s3tests.functional.test_s3.test_bucket_notexist. 
- [Splunk] Fixed the issue of bad_amz_date_epoch test cases on the bucket and object creation. 
- [Splunk] Fixed the issue of s3tests.functional.test_s3:test_bucket_create_naming_bad_punctuation fails.
- [Splunk] Fixed the issue of s3server crash in s3tests.functional.test_s3.test_multipart_upload_empty. 
- [Splunk] Fixed the s3tests.functional.test_s3:test_bucket_create_naming_bad_punctuation issue in S3 Auth Server. 
- [Splunk] Fixed the test_object_requestid_matchs_header_on_error issue. 
- Fixed the issue of calling the UploadPart operation the Service is unavailable. 
- [Splunk] Fixed the s3tests.functional.test_s3.test_multipart_upload fails issue when it ran against main branch. 
- [Splunk] Fixed the error code mismatch for aws4 bad_ua and bad_auth date cases issue. 
- Updated the HA Proxy.
-	Fixed the issue where the Motr HA interface using the wrong tag.
-	Fixed the issue of consul state is not updating for process failure.
-	Added the license header for Motr data recovery (motr_data_recovery.sh).
-	Update the BE error message.
-	Fixed the issue where the Motr Kernel service is not starting on the remote node.
-	Updated the message description for data inconsistent.
-	Updated the IEM alert message.
-	Optimized the object listing performance.
-	Updated the SSPL support bundle temporary directory path.
-	Fixed the issue of URL decode 'continuation-token' during List Object V2 request validation.
-	Fixed the OVA for the host file and set the salt-master default configuration in case of a single node.
-	Fixed the issue where the unboxing script is failing when the static IP network configuration option is selected.
-	Fixed the issue where the S3 CLI requests fail with "No route to host" error intermittently.
-	Updated the SSL certificates.
-	Fixed the issue where SFTP session returns with non-zero exit code.
-	Updated the JSON structures in the Manifest file.
-	Fixed the issue of dangling web-socket connection.
-	Replaced the UDX with LDP and added the expansion to the summary page.
-	Added the post-update command for CSM set-up.
-	Fixed the issue where the shutdown uses the redundant ssh to local host.
-	Added a new SSL certification.
-	Updated the CORTX build locations.