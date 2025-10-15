\###### AWS CLOUD FOUNDATION - ALEXSANDRO LECHNER

Description: Configurar Grupo de Seguranca

Resources:

&nbsp; MinhaInstancia:

&nbsp;   Type: AWS::EC2::Instance

&nbsp;   Properties:

&nbsp;     AvailabilityZone: us-east-1a

&nbsp;     ImageId: ami-0ed9277fb7eb570c9

&nbsp;     InstanceType: t2.micro

&nbsp;     Tags :

&nbsp;       - Key: "Name"

&nbsp;         Value: "Webserver-Firewall"

&nbsp;     UserData:

&nbsp;       Fn::Base64:

&nbsp;         !Sub |

&nbsp;           #!/bin/bash -xe

&nbsp;           yum install -y httpd.x86\_64

&nbsp;           systemctl start httpd.service

&nbsp;           systemctl enable httpd.service

&nbsp;           echo "<h1>OLA AWS FOUNDATIONS do $(hostname -f)</h1>" > /var/www/html/index.html

&nbsp;     SecurityGroups:

&nbsp;     - !Ref GrupoSeguranca



&nbsp; GrupoSeguranca:

&nbsp;   Type: AWS::EC2::SecurityGroup

&nbsp;   Properties:

&nbsp;     GroupDescription: Acesso Liberado Porta 80

&nbsp;     SecurityGroupIngress:

&nbsp;     - IpProtocol: tcp

&nbsp;       FromPort: 80

&nbsp;       ToPort: 80

&nbsp;       CidrIp: 0.0.0.0/0



