- sits on top of UI library making it a complete application framework


It uses UI lib and add:
- file based routing
- server side rendering
- static generation
- api route
- middleware
- deployment

# how it works

you define route (where to fetch data from) and framework decide when to fetch it : either server, client or both.

**SSR**: Produce full html on server side by fetching data and *render HTML on the fly*  

![SSR](assets/ssr.png)

**CSR**: SPA

![SPA](assets/spa.png)

**SSG**: Framework pre-renders all pages to static HTML at build time.

![SSG](assets/ssg.png)

**ISR**: : Page is pre-rendered like SSG, but after a set time (e.g., 60 seconds), the next request triggers a background re-render with fresh data  
**Hybrid / Partial Hydration**: Some part only stays on server and other part get's shipped to client where it hydrates.

> here,  you write code in the same project, but some code runs on the server and some runs in the browser.

```
Most production apps use meta frameworks because they give you the best of all worlds. You can have:

    A statically generated marketing page (/about)
    A server-rendered product page (/products/123)
    A client-side interactive dashboard (/dashboard)
    All in the same project, deployed to the same platform (Vercel/Netlify)
```
