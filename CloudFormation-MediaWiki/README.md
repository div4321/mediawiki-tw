# MEDIAWIKI AUTODEPLOYEMENT USING CloudFormation

**media-wiki.yaml** is the root cfn template where all other cfb templates are nested into the root templates.

For execution save all the templates in a S3 bucket and make sure to provide S3 URL of all nested tempalates in the root **'media-wiki.yaml'** template.



**This code was created to achieve a basic distributed architecture  but in case of need, code can be expanded to incorporate FT & HA using AWS ASG, AWS ALB & AWS Route 53.** 


