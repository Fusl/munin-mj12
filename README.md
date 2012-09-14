Munin MJ12Monitor Statistics
============================

mj12_ - Wildcard-plugin to monitor majestic12 nodes.

How to Use:

1. Download the file to /usr/share/munin/plugins/mj12_

2. Link the file to /etc/munin/plugins/mj12_<ID or randomic numbers>

3. Configure the plugin in /etc/munin/plugin-conf.d/munin-node with these configuration values:

[mj12_<ID or randomic numbers>]
env.host 127.0.0.1
env.port 1088
env.user majesticuser
env.pass secret

4. Download xur17's MJ12Monitor.jhh (https://github.com/xur17/MJ12Monitor/blob/master/MJ12Monitor.jhh) to your Majestic12 node folder into the subfolder htdocs/tools/. It should be available at http://<ip>:<port>/tools/MJ12Monitor.jhh and no, you have not to restart your nodes.

5. Restart the node with /etc/init.d/munin restart

6. Watch the statistics coming up.

This plugin does not normally require configuration but it needs
xur17's MJ12monitor.jhh, which you can find here:
https://github.com/xur17/MJ12Monitor/blob/master/MJ12Monitor.jhh
A copy of this file is located here:
http://dontrm.org/8212858d1d99b57cdc5f9fb3cc9474c7
You must put these files into the /htdocs/tools/ directory of your
majestic12 node to work properly.

If your server does not listens to 127.0.0.1 to port 1088 or your
username and password are not empty you must specify some
configuration values as showed in this sample:

  [mj12_1]
    env.host 127.0.0.1
    env.port 1088
    env.user majesticuser
    env.pass secret

This is a wildcard plugin. To monitor an majestic12 node, link mj12_
to this file. E.g.

  ln -s /usr/share/munin/plugins/mj12_ /etc/munin/plugins/mj12_1

...will monitor the first specified server.
