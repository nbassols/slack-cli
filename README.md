# slack-cli <sub><sup>| Slack on the command line via pure bash</sup></sub>
[![version](http://img.shields.io/badge/version-v0.3.1-blue.svg)](https://github.com/rockymadden/slack-cli/releases)
[![versioning](http://img.shields.io/badge/versioning-semver-blue.svg)](http://semver.org/)
[![branching](http://img.shields.io/badge/branching-github%20flow-blue.svg)](https://guides.github.com/introduction/flow/)
[![license](http://img.shields.io/badge/license-mit-blue.svg)](https://opensource.org/licenses/MIT)
[![status](http://img.shields.io/badge/status-working-brightgreen.svg)](#)

## Installation
```bash
$ brew tap rockymadden/rockymadden
$ brew install slack-cli
```
> __NOTE:__ Requires that your Slack team has one or more
[incoming webhook integrations](https://api.slack.com/incoming-webhooks)

## Usage

```bash
$ slack --help
Usage:
  slack init [--webhook|-w <webhook>] [--channel|-c <channel>] [--username|-u <username>] [--icon|-i <icon>] [--silent|-s]
  slack send [text] [--text|-t <text>] [--channel|-c <channel>] [--silent|-s]
  slack sendtmpl event [--event=<event>] [--title=<title>] [--link=<link>] [--details=<details>] [--color=<color>] [--channel|-c <channel>] [--silent|-s]
  slack sendtmpl task [--what=<what>] [--why=<why>] [--when=<when>] [--color=<color>] [--channel|-c <channel>] [--silent|-s]

Settings Commands:
  init     Initialize default settings

Messaging Commands:
  send               Send a message
  sendtmpl event     Send an event templated message
  sendtmpl task      Send a task notification templated message
```

> __NOTE:__ All subcommands prompt for required arguments which were not provided via options. This
allows for both traditional option-based usage and also prompt-based usage.

### Initialize:

```bash
$ slack init
Enter webhook (e.g. https://hooks.slack.com/services/XXX/XXX/XXX): https://hooks.slack.com/services/XXX/XXX/XXX
Enter default channel (e.g. #general): #general
Enter username (e.g. username-bot): username-bot
Enter emoji (e.g. :robot_face:): :robot_face:
Initializing: done
```

### Send a message:

```bash
$ slack send 'Hello World!'
Sending: done
```

```bash
$ slack send 'Hello World!' --channel='@username'
Sending: done
```

```bash
$ slack send
Enter message (e.g. Hello World!): Hello World!
Sending: done
```

```bash
$ slack send --channel='@username'
Enter message (e.g. Hello World!): Hello World!
Sending: done
```

### Send a templated message:

#### Event template:

![Event Example](http://share.rockymadden.com/image/1D121I1O1c2T/Image%202015-12-05%20at%208.31.03%20PM.png)

```bash
$ slack sendtmpl event
Enter event (e.g. New version of slack-cli released): New version of slack-cli released
Enter title (e.g. v0.2.0): v0.2.0
Enter link (e.g https://github.com/rockymadden/slack-cli/releases/tag/v0.2.0): https://github.com/rockymadden/slack-cli/releases/tag/v0.2.0
Enter details (e.g Introduces new templated messages): Introduces new templated messages
Sending: done
```

#### Task notification template:

![Task Notification Example](http://share.rockymadden.com/image/3N2t402L0b3Q/Image%202015-12-05%20at%207.45.21%20PM.png)

```bash
$ slack sendtmpl task
Enter what (e.g. Restarting server): Restarting database server #3
Enter why (e.g. Out of memory): Out of memory
Enter when (e.g. 15:45, Now): 15:45
Sending: done
```

## License
```
The MIT License (MIT)

Copyright (c) 2015 Rocky Madden (https://rockymadden.com/)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
