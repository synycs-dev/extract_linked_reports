# Setting up SMTP

SMTP is the standard protocol for transmitting email messages over the internet. Configure SMTP to enable SynOps to send smart notifications to users about events and actions related to cloud cost optimization in their infrastructure.

To set up SMTP on a custom SynOps deployment:

1\. Fill in these fields in overlay/user_template.yml ([SynOps/SynOps-deploy/overlay/user_template.yml](../synops-deploy/overlay/user_template.yml)):

```
# SMTP server and credentials used for sending emails
smtp:
  server:
  email:
  login:
  port:
  password:
  protocol:
```

2\. Restart the cluster with the updated user_template.yml:

```
./runkube.py --with-elk  -o overlay/user_template.yml -- <deployment name> <version>
```

3\. If emails are still missing after smtp configured, check the errors in [kibana](kibana_logs.md) using query `name: *heraldengine*`.
