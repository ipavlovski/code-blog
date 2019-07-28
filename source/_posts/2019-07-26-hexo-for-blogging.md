---
title: Hexo for Blogging
date: 2019-07-26 17:52:08
tags:
---

Create the file: /lib/system/systemd/hexo-code.service

```
[Service]
WorkingDirectory=/home/ilyapavlovski/blogs/code
ExecStart=/usr/local/bin/hexo server --draft -p 4000
Restart=always
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=hexo
User=ilyapavlovski
Group=ilyapavlovski
Environment=NODE_ENV=production
[Install]
WantedBy=multi-user.target
```

Ensure the path is correct (likely something npm-based).
: which hexo
: /usr/local/bin/hexo

Start the service
: $ sudo systemctl start hexo-code

Assets:
- global assets (preffered)
- post-based assets (a folder created for each post, much redundancy)

Config changes:
- post title: :year-:month-:day-:title.md 
- post case: 1 -- force lowercase

