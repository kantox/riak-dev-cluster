Riak Dev Cluster for OS X
=========================

Easily run a 5-node [Riak](http://wiki.basho.com/Riak.html) cluster on
OS X.

* The names of the nodes are riak[1-5]@127.0.0.1
* The HTTP port of riak1 is 11098: <http://127.0.0.1:11098>
* Riak Control (Admin UI) is available
    [here](https://admin:admin@127.0.0.1:11098/admin)
* All nodes use the
    [LevelDB](http://docs.basho.com/riak/latest/ops/advanced/backends/leveldb/)
    storage backend [Riak
* Search](http://docs.basho.com/riak/latest/dev/using/search/) is
    disabled (default)
* Please see the `/etc/riak.conf` in each node's directory for the other
    ports and settings

## Getting started

Ensure that [Open File Limits](http://docs.basho.com/riak/latest/ops/tuning/open-files-limit/#Mac-OS-X) are set

Clone and navigate to the repository:

```
$ git clone git://github.com/basho/riak-dev-cluster.git
$ cd riak-dev-cluster
```

There is a `bootstrap` command available that installs, starts, and
joins the Riak cluster in one go:

```
rake bootstrap
```

## Control commands

Start all nodes:

```
rake start
```

Join all nodes as a cluster (only needed once):

```
rake join
```

Stop all nodes:

```
rake stop
```

Clear all data and restart the cluster:

```
rake clear
```

Restart all nodes without clearing all data:

```
rake restart
```

## Riak Data Types

There are a few `rake` commands that will set up your cluster to use
[Riak Data Types](http://docs.basho.com/riak/2.0.0/dev/using/data-types/). You can create a [bucket type](http://docs.basho.com/riak/2.0.2/dev/advanced/bucket-types/) for using [Riak counters](http://docs.basho.com/riak/2.0.2/dev/using/data-types/#Counters) called `counters`:

```
rake counter_bucket
```

You can do the same for sets:

```
rake set_bucket
```

And for maps:

```
rake map_bucket
```

## Other commands

See all available commands by running `rake -T` or just `rake` by itself.

## Note

Depending on your Erlang cookie, you may have to use the commands with `sudo`.

## Development

Basho Labs repos survive because of community contribution. This module has extensive test coverage in order to make contributing easier. Please read [CONTRIBUTING](CONTRIBUTING.md) for details. 

### Maintainers

* [Tyler Hannan](https://github.com/tylerhannan)

You can [read the full guidelines](http://docs.basho.com/riak/latest/community/bugs/) for bug reporting and code contributions on the Riak Docs And **thank you!** Your coontribution is incredibly important to use.

## License and Authors

* [Erick Dennis](https://github.com/edennis)
* [Sebastian Röbke](https://github.com/boosty)
* [Simon Vans-Colina](https://github.com/simonvc)
* [Seth Thomas](https://github.com/cheeseplus)
* [Joel Jacobson](https://github.com/joeljacobson)

Copyright (c) 2015 Basho Technologies, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.

See the License for the specific language governing permissions and
limitations under the License.





