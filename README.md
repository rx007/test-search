# test-search

Example showing how to pre-populate node data using Test Kitchen.

## Overview

The included recipe performs a search and returns some test node data.  To see
the recipe in action, run:

    kitchen converge

To shut down the test VM and release all resources:

    kitchen destroy

Node data is contained in +.json+ files in the +nodes/+ subdirectory of this
cookbook.  Example:

    {
      "name": "node1",
      "chef_type": "node",
      "json_class": "Chef::Node",
      "chef_environment": "_default",
      "run_list": [],
      "automatic": {
        "ipaddress": "192.168.33.31",
        "hostname": "node1"
      }
    }

The easiest way to get the correct file format for this fake node data is to
dump a node from a real Chef Server with the following command, then edit
the values as needed:

    knife node show <node_name> -F json > node.json

## Prerequisites

Clone this repository:

    git clone https://github.com/misheska-cookbooks/demo-mcollective

Install the [Chef Development Kit](http://www.getchef.com/downloads/chef-dk) for your platform.

Install the following virtualization software:

    [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    [Vagrant](https://www.vagrantup.com/downloads.html)