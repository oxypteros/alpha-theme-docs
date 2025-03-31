+++
title = 'Site Search'
date = 2025-03-31T15:29:14+02:00
author = "oxypteros"
draft = false
+++
Alpha is set up to support on-site search function by incorporating the static search library [Pagefind](https://pagefind.app)
To enable the site search function on Alpha you have to:
1. In params.toml (`config/_default/params.toml`) set `pagefind_enabled = true` (default: `false`)
2. Update your build command to include Pagefind indexing, `npx pagefind --site public`[^1]  
Example: 
```bash
hugo --gc --minify && npx pagefind --site public
```
## Cloudflare Pages
If deploying on Cloudflare Pages, update your build command:
1. Go to your Cloudflare Pages project and open the **Settings** tab of your site on the **Workers & Pages** section.
1. Edit the **Build configuration** and set the **Build command** to:  
`hugo --gc --minify && npx pagefind --site public`
1. Click **Save**, then re-deploy your project.

## Vercel
For Vercel deployment:
1. Go to your project’s **Settings** tab
1. Select **Build and Deployment** under **Project Settings**
1. In **Framework Settings**, choose **Override** and set the **Build Command**:
`hugo --gc --minify && npx pagefind --site public`
1. Click **Save**, then re-deploy your project.
[^1]: **Note**: This requires Node.js. If you don’t have it installed, follow the [Node.js installation guide.](/node-install)