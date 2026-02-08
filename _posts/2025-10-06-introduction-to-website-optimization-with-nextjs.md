---
layout: post
title: Introduction to Website Optimization with Next.js
date: 2025-10-06 18:00:00 +0330  # Approximate Gregorian for 1404/09/15
categories: lectures optimization nextjs cloudflare
tags: performance speed webdev
toc: true
---

# Introduction to website optimization with NextJs

In today's fast paced world, speed is everything. With Cloudflare handling around 20% of the entire web understanding optimization methods are a necessity for any developer. Statistics proving over 50% of mobile users leave websites if it takes longer than 5 seconds to load!

## Optimizations discussed

### Cloudflare workers 

**Importance:** Cloudflare Workers run code at the edge (close to users), so we set up automatic Brotli/Gzip for 70% compression and set some custom cache rules.

**How we did it:**
-  A worker script was deployed to force Brotli.
-  Cache logic was added. Caching static assets for 1 year.
-  Result: Noticeable drop in transfer size.

### Proper Header Configuration (`_headers`)

Implementing proper security headers as well as CDN cache rules directly in a `_headers`

**Importance:** CDNs and Browsers cache longer reducing repeating requests.

**Headers that were set:**
- Cache-Control: public, max-age=31536000, immutable (for static files)
- Content-Security-Policy, X-Frame-Options, Strict-Transport-Security for security
- CDN-Cache-Control for Cloudflare edge caching

### Lazy Loading Images

We used NextJs built in `<Image>` component, thus non visible images aren't loaded unless they should be rendered on the DOM as the user scrolls. 

```
<Image
  // ....
  loading="lazy"> // though this is now the default
```

### DNS Prefetch.

As websites continue to make requests on behalf of the user, its important to prefetch fonts, analytics, etc. for external domains.

```
<link rel="dns-prefetch" href="https://fonts.googleapis.com" />
```

## Result

- LCP dropped from 4.5s to 1.7s !

![Danesh Computer Science Club](https://github.com/Danesh-CS-Club/cloudflare-optimization/blob/main/landing%20page.png?raw=true)
