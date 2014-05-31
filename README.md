cf-lastrun

Detect and alert when CFEngine is stuck

## 1. About

Script used to detect and alert when CFEngine is stuck and not applying any
promise for a while (`MAX_SECOND_LATE`)

## 2. Usage

### 2.1. On a system where CFEngine is stuck

```bash
root@host:~# /etc/cron.hourly/cf-lastrun
I'm late ! CFEngine did not run for 13770 seconds ! Check me !
Last /var/cfengine/promise_summary.log line:
1401544020,1401544080: Outcome of version Percolate Promises.cf 1.4 (agent-0):
    Promises observed to be kept 100%, Promises repaired 0%, Promises not
    repaired 0%
root@host:~#
```

### 2.2. On a system where CFEngine is in a good state

```bash
root@host:~# /etc/cron.hourly/cf-lastrun
root@host:~#
```

## 3. Installation

Ideally you want to run this script hourly and get its output by email.
It's easy to do on any debian based system:

```bash
root@host:~# cp cf-lastrunsummary /etc/cron.hourly/cf-lastrun
root@host:~# chmod +x /etc/cron.hourly/cf-lastrun
```

## 4. Licensing

cf-lastrun
Copyright (C) 2012  Percolate Industries, Inc.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
