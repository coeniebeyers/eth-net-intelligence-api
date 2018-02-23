Ethereum Network Intelligence API
============
```
git clone https://github.com/coeniebeyers/eth-net-intelligence-api.git
cd eth-net-intelligence-api
npm install
sudo npm install -g pm2
```

Edit `app.json`
```
[
  {
    "name"              : "node-app",
    "script"            : "app.js",
    "log_date_format"   : "YYYY-MM-DD HH:mm Z",
    "merge_logs"        : false,
    "watch"             : false,
    "max_restarts"      : 10,
    "exec_interpreter"  : "node",
    "exec_mode"         : "fork_mode",
    "env":
    {
      "NODE_ENV"        : "production",
      "RPC_HOST"        : "localhost",
      "RPC_PORT"        : "20010",
      "LISTENING_PORT"  : "20000",
      "INSTANCE_NAME"   : "<fill in>",
      "CONTACT_DETAILS" : "",
      "WS_SERVER"       : "http://<fill in>:80",
      "WS_SECRET"       : "<fill in>",
      "VERBOSITY"       : 2
    }
  }
]
```

Start by using pm2:
```
pm2 start app.json
```

Firewall rules:
1. Outbound connections to the port used by the frontend (typically 3000, 8080, or 80) need to be allowed.
2. If not co-located with your node (not recommended), outbound connections to the RPC port of your node (20010 in the config above) also need to be allowed on the machine running the eth-net-stats-api, as well as inbound connections to the RPC port (also 20010) on the machine running your node. In this case, outbound connections to the node port (20000 in configuration above) would also need to be allowed.

