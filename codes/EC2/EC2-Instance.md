'''YAML

\###### AWS CLOUD FOUNDATION - ALEXSANDRO LECHNER

Description: Criar um Amazon EC2 simples

Resources:

&nbsp; MinhaInstancia:

&nbsp;   Type: AWS::EC2::Instance

&nbsp;   Properties:

&nbsp;     AvailabilityZone: us-east-1a

&nbsp;     ImageId: ami-0ed9277fb7eb570c9

&nbsp;     InstanceType: t2.micro

&nbsp;     Tags :

&nbsp;       - Key: "Name"

&nbsp;         Value: "EC2"      

&nbsp;   

'''

