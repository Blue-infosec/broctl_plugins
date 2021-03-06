![PacketSled Logo](https://packetsled.com/wp-content/themes/freshbiz/img/packetsled-logo.png)
# PacketSled BroControl Plugins

## Snapshot
The Snapshot Plugin allows BroControl to take an immediate snapshot of the running configuration of a given Bro instance. This snapshot may, then, be reverted later.

### Installation
* Copy "snapshot.py" to ${BroBase}/lib/broctl/plugins/snapshot.py

### Broctl Options
~~~
snapshot.list [-v]               - List Available Snapshots
snapshot.remove <identifier>     - Remove the Snapshot of the Bro Configuration Specified by Identifier
snapshot.revert <identifier>     - Revert the Bro Configuration to the Identifier Specified
snapshot.revertfile <path>       - Revert a Snapshot-formatted File
snapshot.take [<identifier>]     - Take a Snapshot of the Current Bro Configuration
~~~

### broctl.cfg Options
Option  | Usage   | Example
------- | ------- | -------
snapshot.option | Space separated list of paths or files to explicitly backup | snapshot.option = /usr/local/bro/lib/bro/plugins /usr/local/bro/etc /usr/local/bro/share/bro
snapshot.dest | Full path to write the backup file (${BroBase}/snapshots is the default) | snapshot.dest = /data/snapshots
snapshot.exclude | Space separated list of paths or files to explicitly exclude from the snapshot | snapshot.exclude = broctl

### Note
* "broctl snapshot.take" without an identifier option will result in a timestamp being used as the identifier
* Bro will have to be restarted for any configuration changes to be applied
 - broctl deploy

# License

GPL

Copyright (c) 2015, Packetsled. All rights reserved.

snapshot is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

snapshot is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with snapshot.  If not, see <http://www.gnu.org/licenses/>.
