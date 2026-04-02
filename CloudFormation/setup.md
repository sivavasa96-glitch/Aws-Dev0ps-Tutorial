Setup using AWS Console (Step-by-step):
====================================

    1.Login to AWS → go to CloudFormation

    2.Click Create stack → With new resources (standard)

Under Prepare template → choose Template is ready

Under Template source → choose one:

Upload a template file (upload s3.yaml)

or Amazon S3 URL (if template is in S3)

Click Next

Enter:

Stack name (example: demo-s3-stack)

If template has Parameters, fill them

Click Next

Configure options (optional):

Tags, IAM role, rollback, notifications

Review page:

If IAM resources exist, tick “I acknowledge…”

Click Create stack

Watch Events tab → wait for CREATE_COMPLETE