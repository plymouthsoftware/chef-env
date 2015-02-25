chef-env
========

Manage multiple chef configurations in isolation from one central location (something like [rbenv](https://github.com/sstephenson/rbenv) for chef)

Installation
-----
    $ git clone git@github.com:plymouthsoftware/chef-env.git
    $ cd chef-env
    $ chmod u+x ./chef-env
    $ chef-env help

Setup
-----
    $ cp ~/.chef ~/.chef.bak # backup your existing ~/.chef folder just in case!
    $ chef-env init # moves any existing ~/.chef to ~/.chef-configs/default

Usage
-----
    $ chef-env list
      List of chef configurations available in ~/.chef-configs
        default
        other-org

    $ chef-env use default
    $ knife node list
      organisationA-node1
      organisationA-node2

    $ chef-env use other-org
    $ knife node list
      organisationB-node1
      organisationB-node2
      organisationB-node3

    $ chef-env clear
    $ knife node list
      [Fail, no configuration at ~/.chef]
