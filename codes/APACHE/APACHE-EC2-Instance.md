'''YAML

\###### AWS CLOUD FOUNDATION - ALEXSANDRO LECHNER

Description: Instalar Servidor Apache

Resources:

&nbsp; MinhaInstancia:

&nbsp;   Type: AWS::EC2::Instance

&nbsp;   Properties:

&nbsp;     AvailabilityZone: us-east-1a

&nbsp;     ImageId: ami-0ed9277fb7eb570c9

&nbsp;     InstanceType: t2.micro

&nbsp;     Tags :

&nbsp;       - Key: "Name"

&nbsp;         Value: "Webserver-Apache"

&nbsp;     UserData:

&nbsp;       Fn::Base64:

&nbsp;         !Sub |

&nbsp;           #!/bin/bash -xe

&nbsp;           yum install -y httpd.x86\_64

&nbsp;           systemctl start httpd.service

&nbsp;           systemctl enable httpd.service

&nbsp;           echo "<h1>OLA AWS FOUNDATIONS do $(hostname -f)</h1>" > /var/www/html/index.html



'''



