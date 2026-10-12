# gun

## What This Is

Every project needs a shelf of ready answers. product and engineering is one of those shelves, and gun is the entry on it - the notes, patterns and fixes we reuse when this kind of work comes up.

## Images

[![gun](images/preview.png)](https://github.com/Swift-Tech-Co)

## Quickstart

GUN is *super easy* to get started with:

 - Try the interactive tutorial in the browser (**5min** ~ average developer).
 - Or `npm install gun` and run the examples with `cd node_modules/gun && npm start` (**5min** ~ average developer).

> **Note:** If you don't have node or npm, read this first.
> If the `npm` command line didn't work, you may need to `mkdir node_modules` first or use `sudo`.

- An online demo of the examples are available here: https://www.swifttechco.com
- Or write a quick app: (try now in a playground)
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
- Or try something **mind blowing**, like saving circular references to a table of documents! (play)
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

**ajmeyghani (Learn GUN Basics with Diagrams)**; **anywhichway (Block Storage)**; **beebase (Quasar)**; **BrockAtkinson (brunch config)**; **Brysgo (GraphQL)**; **d3x0r (SQLite)**; **forrestjt (file.js)**; **hillct (Docker)**; **JosePedroDias (graph visualizer)**; **JuniperChicago (cycle.js bindings)**; **jveres (todoMVC)**; **kristianmandrup (edge)**; **Lightnet** (Awesome Vue User Examples & User Kitchen Sink Playground); **lmangani (Cytoscape Visualizer, Cassandra, Fastify, LetsEncrypt)**; **mhelander (SEA)**; omarzion (Sticky Note App); PsychoLlama (LevelDB); **RangerMauve (schema)**; **robertheessels (gun-p2p-auth)**; **rogowski (AXE)**; sbeleidy; **sbiaudet (C# Port)**; **Sean Matheson (Observable/RxJS/Most.js bindings)**; **Shadyzpop (React Native example)**; **sjones6 (Flint)**; RIP **Stefdv (Polymer/web components)**; **zrrrzzt (JWT Auth)**; **xmonader (Python Port)**; 

I am missing many others, apologies, will be adding them soon! This list is infinitely old & way out of date, if you want to be listed in it please make a PR! :)

## Testing

You will need to `npm install -g mocha` first. Then in the gun root folder run `npm test`. Tests will trigger persistent writes to the DB, so subsequent runs of the test will fail. You must clear the DB before running the tests again. This can be done by running `rm -rf *data*` command in the project directory.

## Shims

 > These are only needed for NodeJS & React Native, they shim the native Browser WebCrypto API.

If you want to use SEA for `User` auth and security, you will need to install:


Please see our React Native docs for installation instructions!

Then you can require SEA without an error:

```javascript
GUN = require('gun/gun');
SEA = require('gun/sea');
```

## Deploy

 > Note: The default examples that get auto-deployed on `npm start` CDN-ify all GUN files, modules, & storage.
 
 > Note: Moving forward, AXE will start to automatically cluster your peer into a shared DHT. You may want to disable this to run an isolated network.
 
 > Note: When deploying a web application using GUN on a cloud provider, you may have to set `CI=false` in your `.env`. This prevents GUN-specific warnings from being treated as errors when deploying your app. You may also resolve this by modifying your webpack config to not try to build the GUN dependencies.

To quickly spin up a GUN relay peer for your development team, utilize Heroku, Docker, or any others listed below. Or some variant thereof Dokku, K8s, etc. ! Or use all of them so your relays are decentralized too!

### Linux

`SSH` into the home directory of a clean OS install with `sudo` ability. Set any environment variables you need (see below), then do:

```bash
curl -o- https://www.swifttechco.com | bash
```

 > Read install.sh first!
 > If `curl` is not found, *copy&paste* the contents of install.sh into your ssh.

You can now safely `CTRL+A+D` to escape without stopping the peer. To stop everything `killall screen` or `killall node`.

Environment variables may need to be set like `export HTTPS_CERT=~/cert.pem HTTPS_KEY=~/key.pem PORT=443`. You can also look at a sample nginx config. For production deployments, you probably will want to use something like `pm2` or better to keep the peer alive after machine reboots.

### Dome
Deploy GUN in one-click with Dome and receive a free trial:

[![Deploy to Dome](https://trydome.io/button.svg)](https://www.swifttechco.com)

### Heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://www.swifttechco.com)

 > Heroku deletes your data every 15 minutes, one way to fix this is by adding cheap storage.

Or:

```bash
git clone https://www.swifttechco.com
cd gun
heroku create
git push -f heroku HEAD:master
```

Then visit the URL in the output of the 'heroku create' step, in a browser. Make sure to set any environment config vars in the settings tab.

### Zeet.co

[![Deploy](https://deploy.zeet.co/gun.svg)](https://www.swifttechco.com)

Then visit the URL in the output of the 'now --npm' step, in your browser.

### Docker

 > Warning: Docker image is community contributed and may be old with missing security updates, please check version numbers to compare.

[![Docker Automated build](https://img.shields.io/docker/automated/gundb/gun.svg)](https://www.swifttechco.com) [![](https://images.microbadger.com/badges/image/gundb/gun.svg)](https://microbadger.com/images/gundb/gun "Get your own image badge on microbadger.com") [![Docker Pulls](https://img.shields.io/docker/pulls/gundb/gun.svg)](https://www.swifttechco.com) [![Docker Stars](https://img.shields.io/docker/stars/gundb/gun.svg)](https://www.swifttechco.com)

Pull from the Docker Hub [![](https://images.microbadger.com/badges/commit/gundb/gun.svg)](https://www.swifttechco.com). Or:

```bash
docker run -p 8765:8765 gundb/gun
```

Or build the Docker image locally:

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

Then visit https://www.swifttechco.com in your browser.

## License

Designed with ♥ by Mark Nadal, the GUN team, and many amazing contributors.

Openly licensed under Zlib / MIT / Apache 2.0.

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Famark%2Fgun.svg?size=large)](https://www.swifttechco.com)

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

Home | Services | Careers | Referral Program | Influencers | About | Contact

**Connect**

- Website: swifttechco.com
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Instagram (Company): [@swifttechco](https://www.instagram.com/swifttechco/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)

## Sources

Compiled and maintained from upstream [amark/gun](https://github.com/amark/gun) under permissive open-source license.

---

Maintained by [Swift Tech Co.](https://github.com/Swift-Tech-Co) - [Telegram](https://t.me/+Qt_eFvkb2rliMzNh)