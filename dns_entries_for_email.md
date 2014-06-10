## DNS Einträge für E-Mail

Die folgenden DNS Einträge sorgen dafür, dass E-Mails, die wir mit ihrer E-Mail-Adresse schicken, nicht im Spam-Ordner landen.

Bitte wenden sie sich an ihren Webmaster oder ans uns, falls sie Hilfe brauchen.

### DKIM

```
v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCrLHiExVd55zd/IQ/J/mRwSRMAocV/hMB3jXwaHH36d9NaVynQFYV8NaWi69c1veUtRzGt7yAioXqLj7Z4TeEUoOLgrKsn8YnckGs9i3B3tVFB+Ch/4mPhXWiNfNdynHWBcPcbJ8kjEQ2U8y78dHZj1YeRXXVvWob2OaKynO8/lQIDAQAB;
```

### SPF

```
v=spf1 include:amazonses.com include:spf.mandrillapp.com ?all
```
