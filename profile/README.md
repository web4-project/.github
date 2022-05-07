![1444070256569233](https://user-images.githubusercontent.com/898335/167266846-1ad2648f-91c1-4a04-a18d-6dd4d6c7d21c.gif)

# What is Web4?

Web4 is a service that takes new internet services and transforms them into simpler code that older browsers and computers can understand. By running Web4, you should be able to take advantage of modern web features but more naturally for older devices.

# What, technically, is Web4?

Web4 is an ASP.NET Core web server with a plugin architecture for writing web services that target older browsers. We intentionally turn off HTTPS and SSL support. The basic idea is to create code that can proxy a site that requires HTTPS or newer web protocols, handle that on a modern web server, and then turn that into simple, static HTML that older browsers can run. For example:

- Twitter is a Progressive Web App (PWA). This PWA requires the newest web browsers, with Javascript enabled, to run correctly.
- Twitter also has an API that developers can use to access their services directly, which has all kinds of uses, including building new applications.
- If we take those APIs, we can build a web service that can handle reading tweets and processing them on a modern web server (ASP.NET Core) and then translate that into a simple HTML template.

Older web browsers, including very early ones like Mosiac (Or newer browsers that target old computers, like Microweb), can generally handle basic HTTP requests (Ex. GET, POST, etc.). So long as our web service can serve those requests, we can control all of the newer requests on the server and send those back to the client.

We can think of this as a proxy service—a central point of contact rather than proxying all web traffic on your computer.
How Web4 is Different

Other projects are doing similar things in this space. Web4 is going at it with a different approach.
- [The Old Net](http://theoldnet.com/): A web service that includes various apps for proxying out to other services, such as Wikipedia, the Internet Archive, and a proxy that can be wired into an existing browser to proxy everything to Internet Archive content.
- [FrogFind!](http://frogfind.com/) and [68k.news](68k.news): Headlines From the Future: Like The Old Net, these sites also wrap newer services (DuckDuckGo and Google News) into sites that render on older computers.
- [webone](https://github.com/atauenis/webone): A HTTP proxy that runs locally on your computer. Once set up, it can strip SSL and other elements that can't run on older computers.
- [wrp](https://github.com/tenox7/wrp): A web rendering proxy that turns modern websites into an image map, which can then be rendered on older browsers.

While these projects are all incredible, they also have their limitations. The Old Net is generally focused on archived content and is very limited at accessing newer information. FrogFind and 68k News hit a wall once you get past what is available on those sites. Webone and wrp are run locally on your machine and can get more sites running on older computers, but also don't try to take the resulting content and make it render natively on these machines. For example, while it is nice to run Gmail on Internet Explorer 1.5, it's the same interface as running it on my current web browser. With a little more work, we can turn that into something that can run inside the browser rather than faking it.

# A Local Server

We intend Web4 to run as a local web server. While you can deploy it to the broader web and create a service like FrogFind, we are more focused on those wanting to access new sites with authenticated credentials. These are much harder to handle on an actual web server, but we can target a single user and keep things inside of their instance when run locally. We can keep all authentication handling within the server, leaving the client to handle more straightforward tasks. For these older browsers, it is more evident with the lack of SSL or other protections within the OS. 

# Why is this called "Web4?"

The other webs were taken.