# PuppetDB3 Explorer

### Overview

PuppetDB3 Explorer is a web application for PuppetDB3 that acts as a dashboard and 
lets you explore your Puppet data. 
It is based on [spotify/puppetexplorer](https://github.com/spotify/puppetexplorer) 
and has been extended to support PuppetDB3 (only).

It is made using AngularJS and CoffeeScript and runs entirely on the client
side, so the only backend that is needed is PuppetDB itself and a web server to
share the static resources.

It has the same query language as the popular Puppet module
[dalen-puppetdbquery](https://forge.puppetlabs.com/dalen/puppetdbquery).
This lets you easily filter for a selection of nodes and show the events or
facts for only them. So you can handle hosts as groups without needing to have
predefined groups, just make them up as you need and click on the pie charts to
drill down further. The JavaScript version of this query parser is available as
a separate component so you can use it in your own projects easily,
[node-puppetdbquery](https://github.com/dalen/node-puppetdbquery).

All views in the application are made to be able to link directly to them, so
it is easy to share information you find with coworkers.

It has support for multiple PuppetDB servers.

### Screenshots

##### The dashboard:
![The dashboard](screenshots/dashboard.png)

##### Node search:
![Node search](screenshots/nodelist.png)

##### Events view and filtering:
![Events view](screenshots/events.png)

##### Facts view:
![Facts view](screenshots/facts.png)

### Installation

The recommended way to install it is on the same host as your PuppetDB instance.
Then proxy /api to :8080/pdb/v4 of your PuppetDB instance.
This avoids the need for any [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing) headers.

It is possible to have it on a separate domain from your PuppetDB though. If you
do, make sure you have the correct `Access-Control-Allow-Origin` header and a
`Access-Control-Expose-Headers: X-Records` header.

You need to copy config.js.example to config.js and modify it for your needs.

To simplify installation you can use the
[spotify-puppetexplorer](https://forge.puppetlabs.com/spotify/puppetexplorer)
Puppet module.

### Dependencies

It is using the V4 PuppetDB API from PuppetDB 3.0.

### See also

 * [Puppetboard](https://github.com/nedap/puppetboard)
 * [Foreman](http://theforeman.org/)
 * [Puppet Enterprise](http://puppetlabs.com/puppet/puppet-enterprise)
