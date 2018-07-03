# PeerVis
A way to visually see who is online and connected as a peer in your Holochain app

PeerVis is a "Zome" that you can include in your Holochain app. This means it is a modular unit of code that is standalone, and won't affect the rest of your code.

To add it to your app, do the following.

1. Add the following to the Zomes array in your dna.json
```
  {
    "Name": "peerVis",
    "Desription": "show whos online",
    "CodeFile": "peerVis.js",
    "RibosomeType": "js",
    "Config": {
      "ErrorHandling": "throwErrors"
    },
    "Entries": [
      {
        "Name": "peerLink",
        "DataFormat": "links"
      }
    ],
    "Functions": [
      {
        "Name": "getPeers",
        "CallingType": "json",
        "Exposure": "public"
      }
    ]
  }
```

2. Copy the `peerVis` folder INTO the `dna` folder of your app

3. Copy `peervis.html` and `cytoscape.min.js` into the `ui` folder of your app

## How to use it
When you're running your application, navigate to the localhost address of your app, plus the path `/peervis.html`. This will dynamically update and show you who how many other nodes are connected to your node, that the app will be gossiping with.


