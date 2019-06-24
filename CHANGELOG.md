# CHANGELOG

## [Unreleased]

## [1.0.5]
### Added
- Use `systeminformation` module to retrieve system information
- Automatic id/sn generation when detecting the system is Raspbian or Mac OS X

### Fixed
- Missing private ip on Ubuntu 18.04 on any SBC (e.g. Raspberry Pi), because of broken `wireless-tools` npm module

## [1.0.4]
### Fixed
- Fix empty id string issue when running `wstty-agent` without `/tmp/ttt_system` file

## [1.0.3]
### Changed
- Upgrade node-pty to 0.8.1 (latest)
- Regenerate package.json in source directory

## [1.0.2] - 2019-05-13
### Changed
- Change server url of default configuration of development stage to "http://127.0.0.1:6030" to connect wstty-server running on the same machine at development

## [1.0.1] - 2019-05-06
### Changed
- Change default server to https://wstty.tic-tac-toe.io

## [1.0.0] - 2019-04-19
### Added
- v1.0 with `lookup-next-server` feature

## [0.9.9] - 2019-04-18
### Changed
- Merge ttt information from environment variables by specifying `TOE_APP_TTT_ENV_PREFIX` and other environment variables with the specified prefix
- Merge context information from the environment variable `TOE_APP_CONTEXT_EXTRAS` that is a set of key value pairs, each pair is separated by `,` while key and value are separated by `:`.

## [0.9.8] - 2019-02-02
### Added
- `filemgr`: support downloadFile operation

## [0.9.7] - 2019-01-31
### Added
- `bash-by-server`: add _operation_ to configs

## [0.9.6] - 2019-01-30
### Added
- `filemgr`: support templating in `parameters` with the environment variables of agent's process
- `bash-by-server`: support templating in `parameters` with the environment variables of agent's process

## [0.9.5] - 2019-01-29
### Added
- `filemgr`: support readFile operation

## [0.9.4] - 2019-01-29
### Added
- `filemgr`: support env operation

## [0.9.3] - 2019-01-29
### Added
- `filemgr`: support readdir operation

## [0.9.2] - 2019-01-27
### Fixed
- Fix command-sock typo issue

## [0.9.1] - 2019-01-26
### Added
- `bash-by-server`: support progress indication to receiver server (http callback) via UnixSock server specified by environment variable: `WSTTY_AGENT_UNIXSOCK`

## [0.9.0] - 2019-01-24
### Added
- Implement `bash-by-server` service.

## [0.8.5] - 2018-10-23
### Changed
- Yapps use the parent directory of either `app.ls` or `index.js` as application name, in order to support multiple instances of wstty-agent.

## [0.8.3] - 2018-09-17
### Changed
- Yapps upgrade tcp-socket and unix-socket servers.
- Yapps improve the handling of shutdown re-entrance
- Yapps move _optimist_ from BaseApp to yapps.ls as entry
- Yapps move yap-simple-logger in, and code refactorying

### Added
- Yapps add `logger` commands to command-unixsock
- Yapps support ctrl unix-socket with `restart` and `shutdown` commands.

## [0.8.0] - 2018-09-08
### Added
- Yapps upgrade with pidfile / ppidfile supports

## [0.7.8] - 2018-06-01
### Changed
- Update `request` module to 2.87.0

## [0.7.7] - 2019-01-01
### Changed
- Re-submit `http-by-server` event when reconnecting to server and server's instance id is not changed
- Add `request_timeout` and `monitor_timeout` to config.json

## [0.7.5] - 2018-05-03
### Changed
- Update timeout from 30s to 120s
- Improve hostname retrieval on Mac OS X by removing its `lan` postfix (e.g. `grandia.lan`)

## [0.7.4] - 2018-05-26
### Changed
- Use yapps to load `package.json` instead of pkginfo

## [0.7.3] - 2018-05-25
### Added
- Implement `AGENT_EVENT_HTTP_BY_SERVER`
- Use symbolic link to solve closure issue (cross-directory)

## [0.7.2] - 2018-05-24
### Changed
- Use hostname and mac address string (upper-case) to compose device unique identity.

## [0.7.1] - 2018-05-20
### Changed
- Improve pkginfo detection with directly-access to `module` variable by skipping browserify manipulation (storing `module` in the `global.yac-context` variable)

## [0.7.0] - 2018-05-19
### Added
- Implement protocol 0.2.0
- Improve network interface information gathering for Mac OS X

## [0.6.0] - 2017-12-16
### Changed
- Upgrade [socket.io-client](https://github.com/socketio/socket.io-client) from 1.3.7 to 2.0.4, to paired with WsttyServer 0.6.0.

## [0.2.7] - 2017-12-16
### Changed
- Replace [pty.js](https://github.com/chjj/pty.js) with [node-pty](https://github.com/Tyriar/node-pty).

## [0.2.6] - 2017-12-15
### Changed
- Generate unique identity from the mac address of ethernet adapter when `/tmp/ttt_system` is unavailable

## [0.2.5] - 2017-05-02
### Added
- `restart_agent` event to force agent to restart itself immediately

## [0.2.4] - 2017-08-12
### Added
- Add sys output to tty data for notifying server about child process status

## [0.2.2] - 2016-08-18
### Changed
- Change default restart_timeout (`DEFAULT_RESTART_TIMEOUT`) from 1 minute to 20 minutes.

## [0.2.1] - 2016-08-18
### Added
- Restart wstty-agent when disconnected more than `restart_timeout` specified in config.json

## [0.2.0] - 2016-08-15
### Added
- Refactor packet protocol in order to support both `pty.spawn` and `child_process.spawn`
- Support "exec" subcommand from wstty-cli

## [0.1.1] - 2016-08-05
### Changed
- Support `BOARD_PROFILE_ENV` in configuration generation because of https://github.com/yagamy4680/yapps/commit/f74b0736dc01d12e8143a25e5dea9d21241aaabf for wstty-agent

## [0.1.0] - 2016-08-05
### Changed
- Apply new configuration generation algorithm from https://github.com/yagamy4680/yapps/commit/f74b0736dc01d12e8143a25e5dea9d21241aaabf for wstty-agent

## [0.0.5] - 2016-03-13
### Added
- Enable regular-gc

## [0.0.4] - 2015-11-19
### Changed
- Minor upgrade because of `system-info` plugin bugfix for missing Wifi.

## [0.0.3] - 2015-11-18
### Changed
- Minor upgrade because of `system-info` plugin update

## [0.0.2] - 2015-11-09
### Changed
- Enclose `socketio.auth` and `request` modules.

## [0.0.1] - 2015-10-27
### Added
- Initial version of WebSocket TTY Agent.

