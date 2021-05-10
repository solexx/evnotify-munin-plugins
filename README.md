# evnotify-munin-plugins

### Background

These are [Munin](http://munin-monitoring.org/) plugins for monitoring
[EVNotify](https://evnotify.de/) devices.

### Plugins

- **evnotify_soc** Displays state of charge (display and BMS)

### Setup

Just drop the plugins into `/etc/munin/plugins` and restart `munin-node`
and set either `akey` and `password` or `akey` and `token` somewhere in
`/etc/munin/plugin-conf.d/`:

```
[evnotify_*]
env.akey abcdef
env.token abcdef0123456789abc
```

or

```
[evnotify_*]
env.akey abcdef
env.password correcthorsebatterystaple
```

None of the plugins need any special privileges. There is no need to run
them as root.

You need to have `jq` installed as this tool is used for parsing the
JSON returned by the charger's API.

### Examples

Here's my setup with all default graphs:
https://jigsaw.home.well-adjusted.de/munin/evnotify-week.html

### TODO

- [ ] Add TODOs

### Contact

For questions and support, feel free to use the Issue Tracker or drop me an
e-mail at js+github at wim.re.
