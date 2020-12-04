---
title: 'Installation'
excerpt: ''
---

# Installation

# TLDR;

```
version: "3"

services:

  meli:
    image: getmeli/api:next
    restart: unless-stopped
    ports:
      - 127.0.0.1:80:80
      - 127.0.0.1:443:443
    environment:
      MELI_HOST=https://cloud.meli.sh
      MELI_MONGO_URI=mongodb://mongo:27017/meli
      MELI_JWT_SECRET=${MELI_JWT_SECRET?MELI_JWT_SECRET} # openssl rand -hex 32
    volumes:
      - /data/meli:/sites

  mongo:
    image: mongo:4.2-bionic
    volumes:
      - ./data/mongo:/data/db
    ports:
      - 127.0.0.1:27017:27017
```

# TSWM;

- Authentication:
    - [GitHub](/authentication/github)
    - [GitLab](/authentication/gitlab)
    - [Gitea](/authentication/gitea)
    - [Google](/authentication/google)
- [Emails](/installation/emails)
- [Advanced deployment](/installation/advanced)