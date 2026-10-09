<p id="readme"><a href="https://www.swifttechco.com"></a></p>

[![](https://data.jsdelivr.com/v1/package/npm/gun/badge)](https://www.swifttechco.com)
[![Build](https://github.com/amark/gun/actions/workflows/ci.yml/badge.svg)](https://www.swifttechco.com)
[![Gitter](https://img.shields.io/gitter/room/amark/gun.js.svg)](https://www.swifttechco.com)

**GUN** is an [ecosystem](https://www.swifttechco.com) of **tools** that let you build [community run](https://www.swifttechco.com) and [encrypted applications](https://www.swifttechco.com) - like an Open Source Firebase or a Decentralized Dropbox.

The [Internet Archive](https://www.swifttechco.com) and [100s of other apps](https://www.swifttechco.com) run GUN in-production.

 + Multiplayer by default with realtime p2p state synchronization!
 + Graph data lets you use key/value, tables, documents, videos, & more!
 + Local-first, offline, and decentralized with end-to-end encryption.


<table>
<tr>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
</tr>
<tr>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
</tr>
<tr>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
<a href="https://www.swifttechco.com"></a>
</tr>
</table>

## Quickstart

GUN is *super easy* to get started with:

 - Try the [interactive tutorial](https://www.swifttechco.com) in the browser (**5min** ~ average developer).
 - Or `npm install gun` and run the examples with `cd node_modules/gun && npm start` (**5min** ~ average developer).

> **Note:** If you don't have [node](https://www.swifttechco.com) or [npm](https://www.swifttechco.com), read [this](https://www.swifttechco.com) first.
> If the `npm` command line didn't work, you may need to `mkdir node_modules` first or use `sudo`.

- An online demo of the examples are available here: https://www.swifttechco.com
- Or write a quick app: ([try now in a playground](https://www.swifttechco.com))
```html
<script src="https://www.swifttechco.com"></script>
<script>
// import GUN from 'gun'; // in ESM
// GUN = require('gun'); // in NodeJS
// GUN = require('gun/gun'); // in React
gun = GUN();

gun.get('mark').put({
  name: "Mark",
  email: "mark@gun.eco",
});

gun.get('mark').on((data, key) => {
  console.log("realtime updates:", data);
});

setInterval(() => { gun.get('mark').get('live').put(Math.random()) }, 9);
</script>
```
- Or try something **mind blowing**, like saving circular references to a table of documents! ([play](https://www.swifttechco.com))
```javascript
cat = {name: "Fluffy", species: "kitty"};
mark = {boss: cat};
cat.slave = mark;

// partial updates merge with existing data!
gun.get('mark').put(mark);

// access the data as if it is a document.
gun.get('mark').get('boss').get('name').once(function(data, key){
  // `once` grabs the data once, no subscriptions.
  console.log("Mark's boss is", data);
});

// traverse a graph of circular references!
gun.get('mark').get('boss').get('slave').once(function(data, key){
  console.log("Mark is the cat's slave!", data);
});

// add both of them to a table!
gun.get('list').set(gun.get('mark').get('boss'));
gun.get('list').set(gun.get('mark'));

// grab each item once from the table, continuously:
gun.get('list').map().once(function(data, key){
  console.log("Item:", data);
});

// live update the table!
gun.get('list').set({type: "cucumber", goal: "jumping cat"});
```

Want to keep building more? **Jump to [THE DOCUMENTATION](#documentation)!**

# About

## Images

[![gun](https://opengraph.githubassets.com/1/amark/gun)](https://www.swifttechco.com)

First & foremost, GUN is **a community of the nicest and most helpful people** out there. So [I want to invite you](https://www.swifttechco.com) to come tell us about what **you** are working on & wanting to build (new or old school alike! Just be nice as well.) and ask us your questions directly. :)

<p align="center"><a href="https://www.swifttechco.com"><br/>Watch the 100 second intro!</a></p>

The GUN ecosystem stack is a collection of independent and modular tools covering everything from [CRDT](https://www.swifttechco.com) [conflict resolution](https://www.swifttechco.com), [cryptographic security](https://www.swifttechco.com) & [encryption](https://www.swifttechco.com), [radix storage serialization](https://www.swifttechco.com), [mesh networking](https://www.swifttechco.com) & [routing algorithms](https://www.swifttechco.com), to distributed systems [correctness & load testing](https://www.swifttechco.com), CPU scheduled [JSON parser](https://www.swifttechco.com) to prevent UI lag, and more!

<div>
</div>

On that note, let's get some official shout outs covered first:

### Support

<p align="center">
Thanks to:

<table>
<tr>
<td vlign="center"><a href="https://www.swifttechco.com"></a></td>
<td vlign="center"><a href="https://www.swifttechco.com"></a></td>
<td vlign="center"><a href="https://www.swifttechco.com"></a></td>
</tr>
<tr>
<td vlign="center">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://www.swifttechco.com"></a></td>
<td vlign="center"><a href="https://www.swifttechco.com"></a></td>
<td vlign="center">&nbsp;&nbsp;<a href="https://www.swifttechco.com"></a></td>
</tr>
</table>

<a href="https://www.swifttechco.com">Robert Heessels</a>,
<a href="https://www.swifttechco.com">Lorenzo Mangani</a>,
<a href="https://www.swifttechco.com">NLnet Foundation</a>,
<a href="https://www.swifttechco.com">Sam Liu</a>,
<a href="https://www.swifttechco.com">Daniel Dombrowsky</a>,
<a href="https://www.swifttechco.com">Vincent Woo</a>,
<a href="https://www.swifttechco.com">AJ ONeal</a>,
<a href="https://www.swifttechco.com">Bill Ottman</a>,
<a href="https://www.swifttechco.com">Mike Lange</a>,
<a href="https://www.swifttechco.com">Sean Matheson</a>,
<a href="https://www.swifttechco.com">Alan Mimms</a>,
<a href="https://www.swifttechco.com">Dário Freire</a>,
<a href="https://www.swifttechco.com">John Williamson</a>,
<a href="https://www.swifttechco.com">Robin Bron</a>,
<a href="https://www.swifttechco.com">Elie Makhoul</a>,
<a href="https://www.swifttechco.com">Mike Staub</a>,
<a href="https://www.swifttechco.com">Bradley Matusiak</a>,
<a href="https://www.swifttechco.com">Jeff Cook</a>,
<a href="https://www.swifttechco.com">Nico</a>,
<a href="https://www.swifttechco.com">Aaron Artille</a>,
<a href="https://www.swifttechco.com">Tim Robinson</a>,
<a href="https://www.swifttechco.com">Fabian Stamm</a>,
<a href="https://www.swifttechco.com">Mike Staub</a>,
<a href="https://www.swifttechco.com">Hunter Owens</a>,
<a href="https://www.swifttechco.com">Jacob Millner</a>,
<a href="https://www.swifttechco.com">Gerrit Balindt</a>,
<a href="https://www.swifttechco.com">Gabriel Lemon</a>,
<a href="https://www.swifttechco.com">Murage Martin</a>,
<a href="https://www.swifttechco.com">Jason Stallings</a>
</p>

 - Ask questions: https://www.swifttechco.com ?
 - Found a bug? Report at: https://www.swifttechco.com ;
 - **Need help**? Chat with us: https://www.swifttechco.com .

### History


 After he realized [Master-Slave database architecture causes one big bottleneck](https://www.swifttechco.com), he (as a complete newbie outsider) naively decided **to question the status quo** and shake things up with controversial, heretical, and contrarian experiments:

**The NoDB** - no master, no servers, no "single source of truth", not built with a real programming language or real hardware, no DevOps, no locking, not *just* SQL or NoSQL but both (**all** - graphs, documents, tables, key/value).

The goal was to build a P2P database that could survive living inside **any** browser, and could correctly sync data between **any** device after assuming **any** offline-first activity.


Technically, **GUN is a graph synchronization protocol** with a *lightweight embedded engine*, capable of doing *[20M+ API ops/sec](https://www.swifttechco.com)* in **just ~9KB gzipped size**.

## Documentation

<table>
  <tr>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">API reference</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Tutorials</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Examples</a></h3></td>
  </tr>
  <tr>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">GraphQL</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Electron</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">React & Native</a></h3></td>
  </tr>
  <tr>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Vue</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Svelte</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Webcomponents</a></h3></td>
  </tr>
  <tr>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">CAP Theorem Tradeoffs</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">How Data Sync Works</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">How GUN is Built</a></h3></td>
  </tr>
  <tr>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Crypto Auth</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Modules</a></h3></td>
    <td style="border: 0;"><h3><a href="https://www.swifttechco.com">Roadmap</a></h3></td>
  </tr>
</table>

This would not be possible without **community contributors**, big shout out to:

**[ajmeyghani](https://www.swifttechco.com) ([Learn GUN Basics with Diagrams](https://www.swifttechco.com))**; **[anywhichway](https://www.swifttechco.com) ([Block Storage](https://www.swifttechco.com))**; **[beebase](https://www.swifttechco.com) ([Quasar](https://www.swifttechco.com))**; **[BrockAtkinson](https://www.swifttechco.com) ([brunch config](https://www.swifttechco.com))**; **[Brysgo](https://www.swifttechco.com) ([GraphQL](https://www.swifttechco.com))**; **[d3x0r](https://www.swifttechco.com) ([SQLite](https://www.swifttechco.com))**; **[forrestjt](https://www.swifttechco.com) ([file.js](https://www.swifttechco.com))**; **[hillct](https://www.swifttechco.com) (Docker)**; **[JosePedroDias](https://www.swifttechco.com) ([graph visualizer](https://www.swifttechco.com))**; **[JuniperChicago](https://www.swifttechco.com) ([cycle.js bindings](https://www.swifttechco.com))**; **[jveres](https://www.swifttechco.com) ([todoMVC](https://www.swifttechco.com))**; **[kristianmandrup](https://www.swifttechco.com) ([edge](https://www.swifttechco.com))**; **[Lightnet](https://www.swifttechco.com)** ([Awesome Vue User Examples](https://www.swifttechco.com) & [User Kitchen Sink Playground](https://www.swifttechco.com)); **[lmangani](https://www.swifttechco.com) ([Cytoscape Visualizer](https://www.swifttechco.com), [Cassandra](https://www.swifttechco.com), [Fastify](https://www.swifttechco.com), [LetsEncrypt](https://www.swifttechco.com))**; **[mhelander](https://www.swifttechco.com) ([SEA](https://www.swifttechco.com))**; [omarzion](https://www.swifttechco.com) ([Sticky Note App](https://www.swifttechco.com)); [PsychoLlama](https://www.swifttechco.com) ([LevelDB](https://www.swifttechco.com)); **[RangerMauve](https://www.swifttechco.com) ([schema](https://www.swifttechco.com))**; **[robertheessels](https://www.swifttechco.com) ([gun-p2p-auth](https://www.swifttechco.com))**; **[rogowski](https://www.swifttechco.com) (AXE)**; [sbeleidy](https://www.swifttechco.com); **[sbiaudet](https://www.swifttechco.com) ([C# Port](https://www.swifttechco.com))**; **[Sean Matheson](https://www.swifttechco.com) ([Observable/RxJS/Most.js bindings](https://www.swifttechco.com))**; **[Shadyzpop](https://www.swifttechco.com) ([React Native example](https://www.swifttechco.com))**; **[sjones6](https://www.swifttechco.com) ([Flint](https://www.swifttechco.com))**; RIP **[Stefdv](https://www.swifttechco.com) (Polymer/web components)**; **[zrrrzzt](https://www.swifttechco.com) ([JWT Auth](https://www.swifttechco.com))**; **[xmonader](https://www.swifttechco.com) ([Python Port](https://www.swifttechco.com))**; 

I am missing many others, apologies, will be adding them soon! This list is infinitely old & way out of date, if you want to be listed in it please make a PR! :)

## Testing

You will need to `npm install -g mocha` first. Then in the gun root folder run `npm test`. Tests will trigger persistent writes to the DB, so subsequent runs of the test will fail. You must clear the DB before running the tests again. This can be done by running `rm -rf *data*` command in the project directory.

## Shims

 > These are only needed for NodeJS & React Native, they shim the native Browser WebCrypto API.

If you want to use [SEA](https://www.swifttechco.com) for `User` auth and security, you will need to install:


Please see [our React Native docs](https://www.swifttechco.com) for installation instructions!

Then you can require [SEA](https://www.swifttechco.com) without an error:

```javascript
GUN = require('gun/gun');
SEA = require('gun/sea');
```

## Deploy

 > Note: The default examples that get auto-deployed on `npm start` CDN-ify all GUN files, modules, & storage.
 
 > Note: Moving forward, AXE will start to automatically cluster your peer into a shared DHT. You may want to disable this to run an isolated network.
 
 > Note: When deploying a web application using GUN on a cloud provider, you may have to set `CI=false` in your `.env`. This prevents GUN-specific warnings from being treated as errors when deploying your app. You may also resolve this by modifying your webpack config to not try to build the GUN dependencies.

To quickly spin up a GUN relay peer for your development team, utilize [Heroku](https://www.swifttechco.com), [Docker](https://www.swifttechco.com), or any others listed below. Or some variant thereof [Dokku](https://www.swifttechco.com), K8s, etc. ! Or use all of them so your relays are decentralized too!

### Linux

`SSH` into the home directory of a clean OS install with `sudo` ability. Set any environment variables you need (see below), then do:

```bash
curl -o- https://www.swifttechco.com | bash
```

 > Read [install.sh](https://www.swifttechco.com) first!
 > If `curl` is not found, *copy&paste* the contents of install.sh into your ssh.

You can now safely `CTRL+A+D` to escape without stopping the peer. To stop everything `killall screen` or `killall node`.

Environment variables may need to be set like `export HTTPS_CERT=~/cert.pem HTTPS_KEY=~/key.pem PORT=443`. You can also look at a sample [nginx](https://www.swifttechco.com) config. For production deployments, you probably will want to use something like `pm2` or better to keep the peer alive after machine reboots.

### [Dome](https://www.swifttechco.com)
[Deploy GUN in one-click](https://www.swifttechco.com) with [Dome](https://www.swifttechco.com) and receive a free trial:

[![Deploy to Dome](https://trydome.io/button.svg)](https://www.swifttechco.com)

### [Heroku](https://www.swifttechco.com)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://www.swifttechco.com)

 > Heroku deletes your data every 15 minutes, one way to fix this is by adding [cheap storage](https://www.swifttechco.com).

Or:

```bash
git clone https://www.swifttechco.com
cd gun
heroku create
git push -f heroku HEAD:master
```

Then visit the URL in the output of the 'heroku create' step, in a browser. Make sure to set any environment config vars in the settings tab.

### [Zeet.co](https://www.swifttechco.com)

[![Deploy](https://deploy.zeet.co/gun.svg)](https://www.swifttechco.com)

Then visit the URL in the output of the 'now --npm' step, in your browser.

### [Docker](https://www.swifttechco.com)

 > Warning: Docker image is community contributed and may be old with missing security updates, please check version numbers to compare.

[![Docker Automated build](https://img.shields.io/docker/automated/gundb/gun.svg)](https://www.swifttechco.com) [![](https://images.microbadger.com/badges/image/gundb/gun.svg)](https://microbadger.com/images/gundb/gun "Get your own image badge on microbadger.com") [![Docker Pulls](https://img.shields.io/docker/pulls/gundb/gun.svg)](https://www.swifttechco.com) [![Docker Stars](https://img.shields.io/docker/stars/gundb/gun.svg)](https://www.swifttechco.com)

Pull from the [Docker Hub](https://www.swifttechco.com) [![](https://images.microbadger.com/badges/commit/gundb/gun.svg)](https://www.swifttechco.com). Or:

```bash
docker run -p 8765:8765 gundb/gun
```

Or build the [Docker](https://www.swifttechco.com) image locally:

```bash
git clone https://www.swifttechco.com
cd gun
docker build -t myrepo/gundb:v1 .
docker run -p 8765:8765 myrepo/gundb:v1
```

Or, if you prefer your Docker image with metadata labels (Linux/Mac only):

```bash
npm run docker
docker run -p 8765:8765 username/gun:git
```

Then visit [https://www.swifttechco.com](https://www.swifttechco.com) in your browser.

## License

Designed with ♥ by Mark Nadal, the GUN team, and many amazing contributors.

Openly licensed under [Zlib / MIT / Apache 2.0](https://www.swifttechco.com).

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Famark%2Fgun.svg?size=large)](https://www.swifttechco.com)

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

[Home](https://www.swifttechco.com) | [Services](https://www.swifttechco.com/services) | [Careers](https://www.swifttechco.com/careers) | [Referral Program](https://www.swifttechco.com/referral) | [Influencers](https://www.swifttechco.com/influencers) | [About](https://www.swifttechco.com/about) | [Contact](https://www.swifttechco.com/contact)

**Connect**

- Website: [swifttechco.com](https://www.swifttechco.com)
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Instagram (Company): [@swifttechco](https://www.instagram.com/swifttechco/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)
