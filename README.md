

# Chimera's Mobile- and Web Wallet API endpoint
The API servers are currently only used to optimize the communication with the daemon and compress the blockchain.

# How to compile & Deploy

### Prerequisites

You will need a VPS-Server with a running and fully synchronized Chimera Daemon for this API Endpoint.

### Building

Upload everything to your web server.

Set the right permissions:

```
chmod 0777 cache
chmod 0777 config/lastRun.txt
```

Don't forget do modify or add your own Chimera node to config/nodesList.php

# Cron task / Process
Precomputed data are build by another process. This process will call the Chimera daemon and compute blocks into chunks of blocks to reduce network latency.
In order to do so, you will need to run the file blockchain.php with an environment variable "export=true".
This file will shut down after 1h, and has a anti-concurrency mechanism built in.

One way to handle this is by running a cron task each minute with something like:
```
* * * * * root cd /var/www/domain.com/mowallet-api && export generate=true && php blockchain.php
```

### Donate

```
CMRA: cmracYag8GeAjELvfQZafXewWnPe5zUVPQCEVj444uBPJimCSVfT43Q4rCme6TVuxDPpuyUKs8q5PcJWf1w568HtcHUYyc75Gmh
```

```
