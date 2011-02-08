# Masterless Example

Here's how to run this:

    puppet apply --modulepath ./modules manifests/site.pp

This is running puppet local (aka, masterless), with no puppet master.

File urls are relative to the local puppet, too.

Stuff like this;

    puppet:///modules/foo/bar.txt

Will be relative to --modulepath, in the above example, as:

    ./modules/foo/files/bar.txt

## Masterless Features

* storeconfigs still works; requires MySQL if you want nodes to actually share
  data (sqlite is local to each puppet node in masterless)
* files can come from the local puppet, too. You just need to ship them to
  /etc/puppet/modules or wherever your moduledir is.