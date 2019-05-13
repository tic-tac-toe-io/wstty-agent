# CHANGELOG

## [1.0.2] - 2019-05-13
### Changed
- Change server url of default configuration to "127.0.0.1:6030" to connect wstty-server running on the same machine at development stage

## [1.0.1] - 2019-05-13

- Change default server to https://wstty.tic-tac-toe.io

## [1.0.0] - 2019-01-01

- v1.0 with `lookup-next-server` feature

## [0.9.9] - 2019-01-01

- Merge ttt information from environment variables by specifying `TOE_APP_TTT_ENV_PREFIX` and other environment variables with the specified prefix
- Merge context information from the environment variable `TOE_APP_CONTEXT_EXTRAS` that is a set of key value pairs, each pair is separated by `,` while key and value are separated by `:`.

For example, when WsttyAgent is started with these environment variables:

```text
TOE_APP_CONTEXT_EXTRAS=rds:1234,token:xyz
TOE_APP_TTT_ENV_PREFIX=XXX
XXX_PROFILE=abc
XXX_PROFILE_VERSION=1234567
XXX_ID=1234
XXX_SN=9999
```

Then, the `ttt` is updated to :

```json
{
  "profile": "abc",
  "profile_version": "1234567",
  "id": "1234",
  "sn": "9999"
}
```

While, the `context` is added with following json object:

```json
{
  "rds": "1234",
  "token": "xyx"
}
```


## [0.9.8] - 2019-01-01

- `filemgr`: support downloadFile operation

## [0.9.7] - 2019-01-01

- `bash-by-server`: add _operation_ to configs

## [0.9.6] - 2019-01-01

- `filemgr`: support templating in `parameters` with the environment variables of agent's process
- `bash-by-server`: support templating in `parameters` with the environment variables of agent's process

## [0.9.5] - 2019-01-01

- `filemgr`: support readFile operation

## [0.9.4] - 2019-01-01

- `filemgr`: support env operation

## [0.9.3] - 2019-01-01

- `filemgr`: support readdir operation

## [0.9.2] - 2019-01-01

- Fix command-sock typo issue

## [0.9.1] - 2019-01-01

- `bash-by-server`: support progress indication to receiver server (http callback) via UnixSock server specified by environment variable: `WSTTY_AGENT_UNIXSOCK`

## [0.9.0] - 2019-01-01

- Implement `bash-by-server` service.

## [0.8.5] - 2019-01-01

- Yapps use the parent directory of either `app.ls` or `index.js` as application name, in order to support multiple instances of wstty-agent.

## [0.8.3] - 2019-01-01

- Yapps improve the handling of shutdown re-entrance
- Yapps move _optimist_ from BaseApp to yapps.ls as entry
- Yapps move yap-simple-logger in, and code refactorying
- Yapps add `logger` commands to command-unixsock

## [0.8.2] - 2019-01-01

- Yapps upgrade tcp-socket and unix-socket servers.
- Yapps support ctrl unix-socket with `restart` and `shutdown` commands.

## [0.8.1] - 2019-01-01

- Dump HTTP Relay result size instead its content (Some HTTP response body might be large...)

## [0.8.0] - 2019-01-01

- Yapps upgrade with pidfile / ppidfile supports

## [0.7.8] - 2019-01-01

- Update `request` module to 2.87.0

## [0.7.7] - 2019-01-01

- Re-submit `http-by-server` event when reconnecting to server and server's instance id is not changed
- Add `request_timeout` and `monitor_timeout` to config.json

## [0.7.5] - 2019-01-01

- Update timeout from 30s to 120s
- Improve hostname retrieval on Mac OS X by removing its `lan` postfix (e.g. `grandia.lan`)

## [0.7.4] - 2019-01-01

- Use yapps to load `package.json` instead of pkginfo

## [0.7.3] - 2019-01-01

- Implement `AGENT_EVENT_HTTP_BY_SERVER`
- Use symbolic link to solve closure issue (cross-directory)

## [0.7.2] - 2019-01-01

- Use hostname and mac address string (upper-case) to compose device unique identity.

## [0.7.1] - 2019-01-01

- Improve pkginfo detection with directly-access to `module` variable by skipping browserify manipulation (storing `module` in the `global.yac-context` variable)

## [0.7.0] - 2019-01-01

- Implement protocol 0.2.0
- Improve network interface information gathering for Mac OS X

## [0.6.0] - 2019-01-01

- Upgrade [socket.io-client](https://github.com/socketio/socket.io-client) from 1.3.7 to 2.0.4, to paired with WsttyServer 0.6.0.

## [0.2.7] - 2019-01-01

- Replace [pty.js](https://github.com/chjj/pty.js) with [node-pty](https://github.com/Tyriar/node-pty).

## [0.2.6] - 2019-01-01

- Generate unique identity from the mac address of ethernet adapter when `/tmp/ttt_system` is unavailable

## [0.2.5] - 2019-01-01

- `restart_agent` event to force agent to restart itself immediately

## [0.2.4] - 2019-01-01

- Add sys output to tty data for notifying server about child process status

## [0.2.3] - 2019-01-01

- Change default restart_timeout (DEFAULT_RESTART_TIMEOUT) from 1 minute to 20 minutes.

## [0.2.2] - 2019-01-01

- Change default restart_timeout from 1 min to 20 minutes.

## [0.2.1] - 2019-01-01

- Restart wstty-agent when disconnected more than `restart_timeout` specified in config.json

## [0.2.0] - 2019-01-01

- Refactor packet protocol in order to support both `pty.spawn` and `child_process.spawn`
- Support "exec" subcommand from wstty-cli

## [0.1.1] - 2019-01-01

- Support `BOARD_PROFILE_ENV` in configuration generation because of https://github.com/yagamy4680/yapps/commit/f74b0736dc01d12e8143a25e5dea9d21241aaabf for wstty-agent

## [0.1.0] - 2019-01-01

- Apply new configuration generation algorithm from https://github.com/yagamy4680/yapps/commit/f74b0736dc01d12e8143a25e5dea9d21241aaabf for wstty-agent

## [0.0.5] - 2019-01-01

- Enable regular-gc

## [0.0.4] - 2019-01-01

- Minor upgrade because of `system-info` plugin bugfix for missing Wifi.

## [0.0.3] - 2019-01-01

- Minor upgrade because of `system-info` plugin update

## [0.0.2] - 2019-01-01

- Enclose `socketio.auth` and `request` modules.

## [0.0.1] - 2019-01-01

Initial version of WebSocket TTY Agent.

