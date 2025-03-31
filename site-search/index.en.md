+++
title = 'Site Search'
date = 2025-03-31T15:29:14+02:00
author = "oxypteros"
draft = false
+++
Alpha is set up to support on-site search function by incorporating the static search library [Pagefind](https://pagefind.app)
To enable the site search function on Alpha you have to:
1. In params.toml (`config/_default/params.toml`) set `pagefind_enabled = true` (default: `false`)
2. In your build command add `npx pagefind --site public`[^1]  
example: 
```bash
hugo --gc --minify && npx pagefind --site public
```
## Cloudflare
If you deploy on Cloudflare Pages:
1. Go to the Cloudflare Pages **Settings** tab of your site on the **Workers & Pages** section.
2. Edit the **Build configuration** and set as **Build command**:  
`hugo --gc --minify && npx pagefind --site public`

[^1]: You have to have installed the node.js. If you don't please follow the [node install guide](/node-install)