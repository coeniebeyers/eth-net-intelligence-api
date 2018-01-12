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
pm2 start
```
