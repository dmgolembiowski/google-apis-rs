<!---
DO NOT EDIT !
This file was generated automatically from 'src/generator/templates/cli/README.md.mako'
DO NOT EDIT !
-->
The `monitoring3` command-line interface *(CLI)* allows to use most features of the *Google Monitoring* service from the comfort of your terminal.

By default all output is printed to standard out, but flags can be set to direct it into a file independent of your shell's
capabilities. Errors will be printed to standard error, and cause the program's exit code to be non-zero.

If data-structures are requested, these will be returned as pretty-printed JSON, to be useful as input to other tools.

Everything else about the *Monitoring* API can be found at the
[official documentation site](https://cloud.google.com/monitoring/api/).

# Installation and Source Code

Install the command-line interface with cargo using:

```bash
cargo install google-monitoring3-cli
```

Find the source code [on github](https://github.com/Byron/google-apis-rs/tree/main/gen/monitoring3-cli).

# Usage

This documentation was generated from the *Monitoring* API at revision *20220218*. The CLI is at version *4.0.1*.

```bash
monitoring3 [options]
        folders
                time-series-list <name> [-p <v>]... [-o <out>]
        organizations
                time-series-list <name> [-p <v>]... [-o <out>]
        projects
                alert-policies-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                alert-policies-delete <name> [-p <v>]... [-o <out>]
                alert-policies-get <name> [-p <v>]... [-o <out>]
                alert-policies-list <name> [-p <v>]... [-o <out>]
                alert-policies-patch <name> (-r <kv>)... [-p <v>]... [-o <out>]
                collectd-time-series-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                groups-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                groups-delete <name> [-p <v>]... [-o <out>]
                groups-get <name> [-p <v>]... [-o <out>]
                groups-list <name> [-p <v>]... [-o <out>]
                groups-members-list <name> [-p <v>]... [-o <out>]
                groups-update <name> (-r <kv>)... [-p <v>]... [-o <out>]
                metric-descriptors-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                metric-descriptors-delete <name> [-p <v>]... [-o <out>]
                metric-descriptors-get <name> [-p <v>]... [-o <out>]
                metric-descriptors-list <name> [-p <v>]... [-o <out>]
                monitored-resource-descriptors-get <name> [-p <v>]... [-o <out>]
                monitored-resource-descriptors-list <name> [-p <v>]... [-o <out>]
                notification-channel-descriptors-get <name> [-p <v>]... [-o <out>]
                notification-channel-descriptors-list <name> [-p <v>]... [-o <out>]
                notification-channels-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                notification-channels-delete <name> [-p <v>]... [-o <out>]
                notification-channels-get <name> [-p <v>]... [-o <out>]
                notification-channels-get-verification-code <name> (-r <kv>)... [-p <v>]... [-o <out>]
                notification-channels-list <name> [-p <v>]... [-o <out>]
                notification-channels-patch <name> (-r <kv>)... [-p <v>]... [-o <out>]
                notification-channels-send-verification-code <name> (-r <kv>)... [-p <v>]... [-o <out>]
                notification-channels-verify <name> (-r <kv>)... [-p <v>]... [-o <out>]
                time-series-create <name> (-r <kv>)... [-p <v>]... [-o <out>]
                time-series-create-service <name> (-r <kv>)... [-p <v>]... [-o <out>]
                time-series-list <name> [-p <v>]... [-o <out>]
                time-series-query <name> (-r <kv>)... [-p <v>]... [-o <out>]
                uptime-check-configs-create <parent> (-r <kv>)... [-p <v>]... [-o <out>]
                uptime-check-configs-delete <name> [-p <v>]... [-o <out>]
                uptime-check-configs-get <name> [-p <v>]... [-o <out>]
                uptime-check-configs-list <parent> [-p <v>]... [-o <out>]
                uptime-check-configs-patch <name> (-r <kv>)... [-p <v>]... [-o <out>]
        services
                create <parent> (-r <kv>)... [-p <v>]... [-o <out>]
                delete <name> [-p <v>]... [-o <out>]
                get <name> [-p <v>]... [-o <out>]
                list <parent> [-p <v>]... [-o <out>]
                patch <name> (-r <kv>)... [-p <v>]... [-o <out>]
                service-level-objectives-create <parent> (-r <kv>)... [-p <v>]... [-o <out>]
                service-level-objectives-delete <name> [-p <v>]... [-o <out>]
                service-level-objectives-get <name> [-p <v>]... [-o <out>]
                service-level-objectives-list <parent> [-p <v>]... [-o <out>]
                service-level-objectives-patch <name> (-r <kv>)... [-p <v>]... [-o <out>]
        uptime-check-ips
                list [-p <v>]... [-o <out>]
  monitoring3 --help

Configuration:
  [--scope <url>]...
            Specify the authentication a method should be executed in. Each scope
            requires the user to grant this application permission to use it.
            If unset, it defaults to the shortest scope url for a particular method.
  --config-dir <folder>
            A directory into which we will store our persistent data. Defaults to
            a user-writable directory that we will create during the first invocation.
            [default: ~/.google-service-cli]

```

# Configuration

The program will store all persistent data in the `~/.google-service-cli` directory in *JSON* files prefixed with `monitoring3-`.  You can change the directory used to store configuration with the `--config-dir` flag on a per-invocation basis.

More information about the various kinds of persistent data are given in the following paragraphs.

# Authentication

Most APIs require a user to authenticate any request. If this is the case, the [scope][scopes] determines the 
set of permissions granted. The granularity of these is usually no more than *read-only* or *full-access*.

If not set, the system will automatically select the smallest feasible scope, e.g. when invoking a
method that is read-only, it will ask only for a read-only scope. 
You may use the `--scope` flag to specify a scope directly. 
All applicable scopes are documented in the respective method's CLI documentation.

The first time a scope is used, the user is asked for permission. Follow the instructions given 
by the CLI to grant permissions, or to decline.

If a scope was authenticated by the user, the respective information will be stored as *JSON* in the configuration
directory, e.g. `~/.google-service-cli/monitoring3-token-<scope-hash>.json`. No manual management of these tokens
is necessary.

To revoke granted authentication, please refer to the [official documentation][revoke-access].

# Application Secrets

In order to allow any application to use Google services, it will need to be registered using the 
[Google Developer Console][google-dev-console]. APIs the application may use are then enabled for it
one by one. Most APIs can be used for free and have a daily quota.

To allow more comfortable usage of the CLI without forcing anyone to register an own application, the CLI
comes with a default application secret that is configured accordingly. This also means that heavy usage
all around the world may deplete the daily quota.

You can workaround this limitation by putting your own secrets file at this location: 
`~/.google-service-cli/monitoring3-secret.json`, assuming that the required *monitoring* API 
was enabled for it. Such a secret file can be downloaded in the *Google Developer Console* at 
*APIs & auth -> Credentials -> Download JSON* and used as is.

Learn more about how to setup Google projects and enable APIs using the [official documentation][google-project-new].


# Debugging

Even though the CLI does its best to provide usable error messages, sometimes it might be desirable to know
what exactly led to a particular issue. This is done by allowing all client-server communication to be 
output to standard error *as-is*.

The `--debug` flag will print errors using the `Debug` representation to standard error.

You may consider redirecting standard error into a file for ease of use, e.g. `monitoring3 --debug <resource> <method> [options] 2>debug.txt`.


[scopes]: https://developers.google.com/+/api/oauth#scopes
[revoke-access]: http://webapps.stackexchange.com/a/30849
[google-dev-console]: https://console.developers.google.com/
[google-project-new]: https://developers.google.com/console/help/new/
