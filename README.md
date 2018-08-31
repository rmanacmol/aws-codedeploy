
# AWS Codedeploy from Bitbucket
--------------------------

* When server is booted run the following commands

sudo su

yum -y update

yum install -y aws-cli

cd /home/ec2-user

* Setup your AWS access, secret, and region.

aws configure 

aws s3 cp s3://aws-codedeploy-us-west-1/latest/install . --region us-west-1

chmod +x ./install

sed -i "s/sleep(.*)/sleep(10)/" install 

./install auto

* Verify status

service codedeploy-agent status 