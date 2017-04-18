# bitcoin-elixir

Bitcoin script and protocol tools plus a full node implementation written in Elxir.

It's still work in progress, not suitable for any kind of usage. Contributions and comments are of course very much welcome,
but if you want to jump in, I'd suggest to get in touch (through github issues) because all APIs are still evolving.

Project is a fork of Justin Lynn's [Bitcoin-Ex](https://github.com/justinlynn/bitcoin-ex) which contained excellent 
protocol parsers and DNS peer discovery.

## Current status

* Full protocol parser and serialization
* Basic script interpreter, but still missing many BIPs (currently 1021/1193 of bitcoin core script tests json)
* Connecting and accepting connections from other peers
* Fetching blockchain to a temporary memory storage (but only with very lacking blcoks and tx validation)

## Roadmap

* Some decent storage backend (postgres or mnesia)
* More strict validation
* Mempool
* BIPs implementation and script fixes to be able to pass all bitcoin core script and transaction tests
* Pass TheBlueMatt's [test-scripts](https://github.com/TheBlueMatt/test-scripts)
* Make sure the architecture allows to easily plug in custom modules so that blockchain / bitcoin network stats can be collected
* Allow it to run across multiple nodes

## Why?

It's handy to have Bitcoin tools for operatino on addresss, transactions and scripts in the language of your choice.
Regarding full node, because it's fun. Given that Bitcoin protocol is defined by the reference client, playing with your
own implementation is one of a very few ways to truly understand how Bitcoin works. It is not meant to be used as a wallet.

## Running the node

To start a node uncomment the following line in the dev.exs

    # config :bitcoin, :node, []

To avoid abusing the network you may want to only connect to your local node e.g.:

    config :bitcoin, :node, [
      connect: [{127.0.0.1}]
    ]

## Licence

See the LICENCE file in the project root.

## Contributing

Please fork this repository to your own account, create a feature/{short but descriptive name} branch on your own
repository and submit a pull request back to develop.

**Any** kind of contributions are super welcome. Even if it's a comment bitching about how things are done currently.



