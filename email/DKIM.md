When using DKIM keys, take off the semicolon at the end from the string supplied by Worxware if you use their service.

They supplied:
```
yourSelectorHere._domainkey   IN  TXT "v=DKIM1; k=rsa; g=*; s=email; h=sha1; t=s; p=yourSuperLongHashGoesHEre;"
```

And you'd want to just copy this into your TXT record:

`v=DKIM1; k=rsa; g=*; s=email; h=sha1; t=s; p=yourSuperLongHashGoesHEre`