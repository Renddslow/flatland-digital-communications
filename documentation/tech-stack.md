# Flatland Church Technology Stack
At Flatland Church we attempt to stay up to date with current development trends in an effort to not only serve our church, but to also provided new or junior developers an opportunity to develop with modern development stacks.
The following is a brief outline of our technology stack and core architecture.

## Platforms
At Flatland Church we have three core platforms: flatlandchurch.com, Flatland native, and flatland.church, along with some management tools and our API.

### flatlandchurch.com
Our primary site and landing page, flatlandchurch.com is designed to reach people who have never come to Flatland before or who attend but are not plugged in. Our primary goal for flatlandchurch.com is to move people from non-attenders to attenders and from attenders to volunteers.

#### Stack
- Angular 4 Universal (the entire site is run on the client)
- Express.js (for server-side rendering)
- NGINX (we run a proxy pass to the express server)
- Flatland API (our in-house API for all content, see below)

[Fork it on GitHub](https://github.com/Renddslow/flatland-angular)

### api.flatlandchurch.com/v1
Version 1 of our API primarily served our original Python/Flask web site. This API is considered deprecated, with all development having ceased on it, however the site will continue to rely on a few endpoints from v1 until all data has been moved to v2.

#### Stack
- Python
- Flask (a micro-framework for handling requests)
- uWSGI (reverse-proxy server)
- NGINX (proxy pass to uwsgi)
- mySQL

*Not available on GitHub*

### api.flatlandchurch.com/v2
Version 2 of our API is the current source for all data on the current Flatland sites (and soon apps). The new API is considerably more flexible and has a smoother learning curve compared to it's Pythonic counterpart.

#### Stack
- Express.js
- Firebase (all new data lives in Firebase, as well web admin auth)
- mySQL (old data, primarily blog, still lives in SQL but will move soon)
- NGINX (proxy pass to express server)

[Fork it on GitHub](https://github.com/Renddslow/flatland-node-api)

### Flatland Native
At this time Flatland's only native properties are its iOS and Android apps. As of October 2017 we are utilizing Subsplash Consulting for management and development of our app, however we expect by the end of the year to bring the app in house on our own stack. Below is an outline of our proposed tech stack.

- Ionic (A Cordova framework that let's you write in Angular 2)
- Urban Airship (For push notifications)


## Cloud Providers
We currently serve the bulk of our content out of a $20/mo **DigitalOcean** droplet. The reason for the size was largely because of mySQL performance. With everything moving to Firebase over the last quarter of 2017 we will likely be able to reduce our server size if not move to a less expensive provider.

Our primary database provider is **Firebase**, which we also use to manage our authentication needs for managing the Flatland website/app in our admin portal. We are currently managing on the free Spark plan, with little chance of needing more than its offerings over the remainder of 2017.
