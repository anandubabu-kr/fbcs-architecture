---
title: "Page"
description: "Initialize your application with FBCS architecture"
pubDate: "Jul 22 2022"
heroImage: "/blog-placeholder-4.jpg"
order: 2
---

## 1. `page/`

> routing and default starting point

It is a next js defined directory to handle routes and apis. A page is actually constructed with the features from the respective feature directory. From each route there will be only a **single** file and export.

The page will import respective features and combine them to form the page

the folder will contain the following directories

### Sub directories

- 1. `api/` - The gate way APIs will be defined here
- 2. `page-x/` - This will be the routes

```
└── page/
      ├── api/
      └── page-x/
```
