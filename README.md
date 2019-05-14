# wstty-agent

Device agent for remote diagnosis over WebSocket. The agent shares its TTY session with end-users via [wstty-server](https://github.com/tic-tac-toe-io/wstty-server) (as cloud relay).


## Quick Start

### Server and Agent at Localhost

Open one terminal window to run [wstty-server](https://github.com/tic-tac-toe-io/wstty-server) docker image:

```text
$ docker run -p 6030:6030 --rm --name wstty-server tictactoe/wstty-server:latest
```

And, open another terminal window to run agent by checking out repository and installing required node modules:

```text
$ cd wstty-agent
$ npm install
$ node ./index.js
```

Then open browser to visit http://localhost:6030/tty to enjoy Web TTY with default user account `test1` (password is same as username).


### Server and Agent at different machines

On the machine to run [wstty-server](https://github.com/tic-tac-toe-io/wstty-server) docker image (assuming the ip address of this machine is `192.168.1.10`):

```text
$ docker run -p 6030:6030 --rm --name wstty-server tictactoe/wstty-server:latest
```


On the machine to run agent, please instruct:

```text
$ cd wstty-agent
$ npm install
$ node ./index.js -s 'wstty-client.url=http://192.168.1.10:6030'
```

Then open browser to visit http://192.168.1.10:6030/tty to enjoy Web TTY with default user account `test1`.



## Todo

- [x] format CHANGELOG.md as https://keepachangelog.com/en/1.0.0/
