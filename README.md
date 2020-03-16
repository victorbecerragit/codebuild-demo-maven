# codebuild-demo-maven
Updated lab from LA DEVOP PRO github

#Tested locally 
OS : Ubuntu
JDK: 11.x 
Added fix to pom.xml to avoid compilation issues for java version.

# Tested on AWS CodeBuild 
# Source:
S3 (should be in the same project region )
 
# env:
OS: Ubuntu
Runtime: Standard
Image : aws/codebuild/standard:2.0

# Artifact:
S3 (should be in the same project region )


#Ref code for Java Spring web svc on EC2 , and nice tip to export logs from CloudWatch

https://devops.stackexchange.com/questions/1336/how-do-i-write-a-buildspec-yml-file

From CloudWatch console:
- click on 'View Logs' link, to find out your Log Group and Log Stream.
- install "awscli" and "jq" in your local term.
- Run substituting your log-group-name and -log-stream-name:

 $aws logs --profile free-tier-lab --region us-west-2 get-log-events \
 --log-group-name  /aws/codebuild/Demo-Maven \
 --log-stream-name 77cdbae0-e5ae-43c9-a652-c8d6a5839404 \
 | jq '.events[].message' -r | grep -v '^$' 
