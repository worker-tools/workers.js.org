# Worker Environments ⚙️

Worker Environments are the new standard for authoring HTTP servers in JavaScript.

## Background
Worker Environments are a derivation of the API outlined in the [Server Workers API][1] working draft, which is a browser standard for offline web applications. To give developers maximum freedom over offline experiences, the API includes a minimal specification for HTTP servers that run inside the browser.

Since it was published, _other vendors have adopted this API for HTTP servers that run in the cloud_, or on the edge in the case of [Cloudflare Workers][2]. Together with Service Workers, they are known as _Worker Environments_, or _Worker Contexts_.

These fulfill the original promise of NodeJS, to use one language and share code between the client and server. In practice, this never came to be and instead these worlds have diverged[^1]. Worker Environments are bringing them back together.  

This is good news for frontend developers in particular: The knowledge ac- and re-quired for building offline web applications can now be applied to writing HTTP servers. 

Worker Environments are an extension to the API Economy: As more functionality moves into 3rd party providers sititng behind HTTP APIs, backends themselves become smaller. In some cases, they are reduced to storing credentials for 3rd party APIs and forwarding calls from the client. Having a fully-fledged node environment with native dependencies, etc. might not be necessary. At the same time, these 
<!-- Cloudflare Workers are more than enough -->

## State of Worker Environments

__There is currently 1 (one) fully-fledged Worker Environment__. There is currently 1 (one) alternative being implemented.


## API Status 
Are We Worker Environment Yet?


| API                     | Service Workers | Cloudflare Workers | Deno Workers |
|:------------------------|:---------------:|:------------------:|:------------:|
| Domain                  | Client          | Edge               | Server       |
| Open Source             | [x]             | [ ]                | [x]          |
| 1.0                     | [x]             | [x]                | [ ]          |

### Browser APIs

| API                     | Service Workers | Cloudflare Workers | Deno Workers |
|:------------------------|:---------------:|:------------------:|:------------:|
| `fetch` event           | [x] | [x] | [?] |
| `install` event         | [x] | [ ] | [?] |
| `activate` event        | [x] | [ ] | [?] |
| Fetch API               | [x] | [x] | [x] |
| Encoding API            | [x] | [x] | [x] |
| URL API                 | [x] | [p] | [x] |
| Streams API             | [p] | [p] | [x] |
| Web Cryptography API    | [x] | [x] | [p] |
| Cache API               | [x] | [p] | [ ] |
| Timers                  | [x] | [x] | [x] |
| `atob` / `btoa`         | [x] | [x] | [x] |
| WebSockets              | [x] | [p] | [x] |
| Abort Controller        | [x] | [d] | [x] |
| IndexedDB               | [x] | [ ] | [ ] |

### Working Drafts
Technically most of the APIs mentioned above are still working drafts. However, they are well supported in current browsers and Worker Environments (as outlined above). The APIs below are not like this. They are either abandoned or do not buy-in from major browser vendors. Yet they can be reasonable targets for 3rd party libraries, such as KV stores or cookie middleware.

| API                     | Service Workers | Cloudflare Workers | Deno Workers |
|:------------------------|:---------------:|:------------------:|:------------:|
| KV Storage API          | [d] | [d] | [?] |
| Cookie Store API        | [p] | [d] | [?] |

### Non-Standard APIs
These are useful APIs provided by one or more Worker Environment that isn't on any kind of standards track (including abandoned). 

| API                     | Service Workers | Cloudflare Workers | Deno Workers |
|:------------------------|:---------------:|:------------------:|:------------:|
| `scheduled` event       | [ ] | [x] | [ ] |
| HTMLWriter              | [ ] | [x] | [ ] |
| Durable Objects         | [ ] | [x] | [ ] |


### Legend

[x]
: Supported
 
[p]
: Partial support 

[d]
: Supported via 3rd party library / polyfill

[?]
: Support to be determined

[ ]
: Not supported


## Frameworks
No HTTP Server is complete without a Web Framework (or rather a gazillion) for common tasks such as routing, sessions, authentication, and more. Worker Environments do not have a complete package yet. However, you can head over to https://worker-utils.github.io for libraries, tools, and guides on how to 

## Contributing
Are you aware of any other Worker Environments available or in development? Did you find any inaccuracies in the tables above? Open a PR!


[1]: https://w3c.github.io/ServiceWorker/
[2]: https://workers.cloudflare.com

***

[^1]: Node and the browser have diverged due to a lack of browser APIs for many crucial components, including HTTP, streams, file access, and more more. A lot has changed since then. Standards have been written for all of these and more, often informed by the experience of using the node-equivalent.
