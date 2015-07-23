                            _ _
       ___  _____  __   ___| (_)
      / _ \/ __\ \/ /  / __| | |
     | (_) \__ \>  <  | (__| | |
      \___/|___/_/\_\  \___|_|_|

# osx-cli

A collection of command line shortcuts for common OS X operations.

This is a work in progress.

## Installation

### Manual

To install manually, simply add the `osx` script to your `$PATH`. If
you already have a `~/bin` directory, you can use the following command:

    curl -L https://raw.github.com/alphabetum/osx-cli/master/osx \
      -o ~/bin/osx && chmod +x ~/bin/osx

## Commands

A selection of included commands. To see the full list, run `osx
commands`.

### `accounts`

```
Usage:
  osx accounts (list | login <username> | window)

Subcommands:
  list    List login user accounts.
  login   Login as the specified user, aka "Fast User Switching."
  window  Go to the OS X login window.
```

### `airport`

```
Usage:
  osx airport (on | off | info | quality | scan | join <SSID>)

Subcommands:
  on       Turn wireless on.
  off      Turn wireless off.
  info     Show the current airport status.
  quality  Show the wireless quality as a percentage.
  scan     Perform a scan for wireless networks.
  join     Join the specified network.
```

### `battery`

```
Usage:
  osx battery [-l|--long]
  osx battery status [-l|--long]
  osx battery cycles
  osx battery health

Subcommands:
  status  Current battery status.
  cycles  Number of battery cycles.
  health  Health of the battery, using the current maximum capacity as
          percentage of the battery's design capacity).

Options:
  -l --long  Print longform information about the battery status.

Description:
  Print battery info. When no subcommand is specified, display `status`.

```

### `caffeinate`

```
Usage:
  osx caffeinate [-disu] [-t timeout] [command] [arguments]

Description:
  Prevent the system from sleeping on behalf of a utility.

  This is simply a bookmark for the caffeinate command.

  See `man caffeinate` for more information.

Examples:
  caffeinate -u -t 3600
    Prevent sleeping for one hour (3,600 seconds).

  caffeinate -s scp bigfile me:myserver/bigfile
    Prevent sleeping until the secure file copy (scp) completes.
```

### `desktop`

```
Usage:
  osx desktop ( hide | show )

Description:
  Hide/show all desktop icons (useful when presenting).
```

### `eject`

```
Usage:
  osx eject <volname>

Description:
  Ejects a given volume (eg, a disk image).
```

### `fans`

```
Usage:
  osx fans

Description:
  Display fan stats via iStats.

  More information:
    https://github.com/Chris911/iStats
```

### `finder`

```
Usage:
  osx finder hidden ( hide | show )

Description:
  Hide/show hidden files in the Finder.
```

### `lock`

```
Usage:
  osx lock

Description:
  Lock the screen (when going AFK).
```

### `login-items`

```
Usage:
  osx login-items list
  osx login-items add <path> [--hide]
  osx login-items delete ( <name> | </path/to/application.app> )

Subcommands:
  list    List current login items.
  add     Add a login item using the full path to the .app.
  delete  Delete a login item using either the name, found via the `list`
          subcommand, or the full path to the item.

Description:
  List, add, and delete login items.

  More information:
    https://hamstergene.github.io/post/editing-osx-login-items-cmdline/
```

### `play`

```
Alias for `afplay`

    Audio File Play
    Version: 2.0
    Copyright 2003-2013, Apple Inc. All Rights Reserved.
    Specify -h (-help) for command options

Usage:
osx play [option...] audio_file

Options: (may appear before or after arguments)
  {-v | --volume} VOLUME
    set the volume for playback of the file
  {-h | --help}
    print help
  { --leaks}
    run leaks analysis
  {-t | --time} TIME
    play for TIME seconds
  {-r | --rate} RATE
    play at playback rate
  {-q | --rQuality} QUALITY
    set the quality used for rate-scaled playback
    (default is 0 - low quality, 1 - high quality)
  {-d | --debug}
    debug print output
```

### `process`

```
Usage:
  osx process pause ( <pid> | -n --name <name> )
  osx process continue ( <pid> | -n --name <name> )
  osx process throttle <pid> <max usage>
  osx process kill ( <pid> | -n --name <name> )

Description:
  Pause, continue, throttle, or kill a given process.

Dependency:
  cputhrottle
    http://www.willnolan.com/cputhrottle/cputhrottle.html
```

### `ql`

```
Usage:
  osx ql <item>

Description:
  Open items with Quick Look.
```

### `sleep`

```
Usage:
  osx sleep

Description:
  Put the system to sleep immediately.
```

### `spotlight`

```
Usage:
  osx spotlight find      <filename>
  osx spotlight filename  <filename>
  osx spotlight content   <text>
  osx spotlight disable
  osx spotlight enable

Description:
  Spotlight searching and controls.
```

### `sshd`

```
Usage:
  osx sshd ( start | stop | status )

Description:
  Start, stop, or get the status of sshd for remote login
```

### `stats`

```
Usage:
  osx stats

Description:
  Display temperature, fan, and battery status via iStats.

  More information:
    https://github.com/Chris911/iStats
```

### `temp`

```
Usage:
  osx temp

Description:
  Display CPU and battery temperature via iStats.

  More information:
    https://github.com/Chris911/iStats
```

### `textutil`

```
Usage:
  osx textutil [command_option] [other_options] file...

Description:
  textutil can be used to manipulate text files of various formats, using the
  mechanisms provided by the Cocoa text system.

  This is simply a bookmark for the system's textutil utility.

  See `man textutil` for more information.

Examples:
  textutil -convert html MyWordFile -output /tmp/webfile.html
    Convert a Word document into HTML.

  textutil -info MyWordFile
    Display information about the file format.
```

### `trash`

```
Usage:
  osx trash ( empty [--secure] [--all] | open )

Subcommands:
  empty  Empty the trash.
  open   Open the trash folder in the finder.

Options:
  --secure  Use `srm` to securely delete trash contents.
  --all     Empty trashes on all connected volumes.
```

### `vnc`

```
Usage:
  osx vnc ( start | stop | status )

Description:
  Start, stop, or get the status of vnc aka Screen Sharing aka Remote Desktop
```

### `volume`

```
Usage:
  osx volume ( <0-9> | <00-100> | mute | unmute )

Arguments:
  <none>    Print the current output volume level as a percent.
  <0-9>     Set the output volume to about the nearest tenth percent. Sometimes
            the actual number is slightly off for reasons unknown.
  <00-100>  Set the output volume to the specified percent.
  mute      Mute output.
  unmute    Unmute output.
```
