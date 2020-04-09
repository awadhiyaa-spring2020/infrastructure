# infrastructure 
Includes json file for aws cloud formation
passing variables using cli

creating policies roles ec2 and rds instances

# Commands related to ssl certificate..
==> command to convert .crt to .pem format used to import in aws
openssl x509 -in mycert.crt -out mycert.pem -outform PEM

# command to import certificate in aws
aws acm import-certificate --certificate fileb://prod_aawadhiya_me.pem --certificate-chain fileb://prod_aawadhiya_me.ca-bundle --private-key fileb://private-key.pem --profile prod

# command to verify certificate 
aws acm list-certificates --certificate-statuses ISSUED --query "CertificateSummaryList[?DomainName=='prod.aawadhiya.me']" --profile prod

# command to get value of certificate arn
Certificate=$(aws acm list-certificates --query 'CertificateSummaryList[0].CertificateArn' --output text)