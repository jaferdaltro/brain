---
apple-notes-id: 32BB05B8-90A6-4F8F-97CB-7701B3DBE7F6
---
```
openssl enc -in foo.bar \
    -aes-256-cbc \
    -pass stdin > foo.bar.enc
```