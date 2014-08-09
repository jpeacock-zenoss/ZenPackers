==========================
General Concepts for CP
==========================

Links for Serviced
=========================

* https://github.com/zenoss/serviced/wiki
* https://github.com/zenoss/serviced/wiki/Starting-CP-Beta

General Links for Zendev
=========================

* http://zenoss.github.io/zendev
* http://zenoss.github.io/zendev/devimg.html

General ZenDev Tasks
===========================

::

   ZOPE=$(serviced service list | grep Zope | awk '{print $2}')

   # Open zendmd
   serviced service run -i $ZOPE zendmd

   # Run zenup
   serviced service run $ZOPE zenup [args…]

   # Install a zenpack in Zendev: Log into container, then do install.
   zendev devshell 
   zenpack --link --install /mnt/src/zenpacks/ZenPacks.zenoss.ControlCenter

   # Install a zenpack
   serviced service run $ZOPE zenpack --link --install ZenPacks.zenoss.ControlCenter

   # Report daemon stats
   serviced service action $DAEMON stats

   # Set daemon to debug
   serviced service action $DAEMON debug

   # Attach
   serviced service attach $SERVICEID bash

   # Shell
   serviced service shell -i $SERVICEID bash

Container Creation Specifics
=============================
::

      # zendev devshell: defaults to a Zope imports
      zendev devshell

      # Create a Zenhub imports environment this way
      zendev devshell zenhub

