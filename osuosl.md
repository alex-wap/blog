---
layout: page 
title: IPMI Management Console
permalink: /osuosl/
---

The following page serves as a wiki for my GSoC '14 project with the OSU OSL.

### Some useful links

   * Code and version history for this page can be found [here](https://github.com/emaadmanzoor/blog/osuosl.md).
   * You can find my proposal [here](http://www.google-melange.com/gsoc/proposal/review/student/google/gsoc2014/emaadmanzoor/5724160613416960).
   * Repository for the code under the OSU OSL [Github organization](https://github.com/osuosl). `TODO`
   * OSL IPMI test machine. `TODO`

### Current Tasks

   * Get access to an IPMI-enabled machine `TODO`
   * Discuss initial REST API and CLI design, REST service hosting `TODO`
   * Implement the `login` and `power` REST endpoints and CLI commands `TODO`

## Design

The standard CLI for IPMI-enabled machines is [ipmitool](http://sourceforge.net/projects/ipmitool/). Since we
expect access from devices that may not have `ipmitool` available (eg. mobile phones), it makes sense to provide
a universal REST API that is served from an OSL machine.

### REST API Endpoints

   * `/login/`: Accepts a username/password combination, issues an auth token on success. All future
     IPMI requests reuse this auth token.
   * `/power/`: Powers on, off or cycle the machine. This wraps the `ipmitool power status|on|off|cycle|reset`
     commands.
   * `/console/`: Returns a persistent connection streaming the output of the SOL console. This wraps
     the `ipmitool sol activate|deactivate` commands.
   * `/sensors/`: Provides sensor readings. This wraps the `ipmitool sdr` commands.
   * `/log/`: Returns the sensor event log. This wraps the `ipmitool sel` commands.

### CLI

I plan for the CLI to make calls to the REST API, retreive the JSON response and format the output
in a suitable way for the screen. The CLI commands will look like the following:

{% highlight bash %}
igor login
igor power -h osl0[1-6] status|on|off|cycle|reset
igor console
igor sensors
igor log
{% endhighlight %}
