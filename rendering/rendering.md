# Client Side Rendering, Server Side Rendering, or Pre-Rendering

## What is it?

| Client Side Rendering                                                       | Server Side Rendering                                                        | Pre-Rendering                                                                                                                             |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Compile HTML pages with static data on server &rarr; `fetch` data on client | `fetch` data on server &rarr; compile HTML pages with fetched data on server | - Compile HTML pages once at build time &rarr; store the cached HTML in a CDN &rarr; return the static cached page <br> - Hybrid approach |
| - React.js <br> - Angular.js                                                | - Java <br> - React on Express.js                                            | - Next.js                                                                                                                                 |

## Pros and Cons

|          | Client Side Rendering                                                 | Server Side Rendering                                                                                                                                                                | Pre-Rendering                                                            |
| -------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| **Pros** | - Fast rendering after initial loading                                | - Good Search Engine Optimization (SEO) <br> - Fast initial loading                                                                                                                  | - Better SEO <br> - Lesser requests than SSR                             |
| **Cons** | - Low SEO as it crawls on the static data <br> - Slow initial loading | - Lots of server requests <br> - Full page reloads <br> - More expensive as it takes up more CPU to compile the HTML pages <br> - Slow rendering when app has a lot of interactivity | - Need to provide user-friendly UI for first loading if data is required |

## Usage

| Client Side Rendering                                                                                        | Server Side Rendering                                                                     | Pre-Rendering                                                                |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| - App has dynamic data and interactive UI <br> - Does not require SEO e.g., internal apps <br> - Large users | - App has minimal interactivity / more static pages <br> - Require SEO <br> - Small users | - If you don’t want to use SSR, but you need to improve loading time and SEO |
