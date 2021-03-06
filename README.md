# ocaml-language-server

A language server for [OCaml](http://ocaml.org) and [Reason](https://reasonml.github.io)

## Overview

The OCaml Language Server is an implementation of the [Language Server
Protocol](https://github.com/Microsoft/language-server-protocol) (LSP) for
OCaml, Reason, and related tooling, including support for BuckleScript.

The OCaml Language Server works by providing a standardized JSON-RPC interface
(via the LSP) to existing OCaml and Reason tooling. This makes it much easier to
provide a uniform development experience across the different editors without
duplication of effort.

The OCaml Language Server is not intended to be a replacement for existing OCaml
and Reason language tooling. It is intended to make existing language
tooling–much of which is excellent and has been developed with great
effort–easier to integrate into editors and more accessible to users without
requiring extensive configuration effort.

## Features

The OCaml Language Server supports the following LSP capabilities and custom
features:

* [x] OCaml support
* [x] Reason support
* [x] BuckleScript [build system](https://bucklescript.github.io/bucklescript/Manual.html#_bucklescript_build_system_code_bsb_code)
* [x] compiler diagnostics
* [x] incremental document synchronization
* [x] code action provider
* [x] code lens provider
* [x] completion provider
* [x] definition provider
* [x] document formatting provider
* [x] document highlight provider
* [x] document range formatting provider (Reason)
* [x] document symbol provider
* [x] hover provider
* [x] references provider
* [x] workspace symbol provider

## Clients

The following editor plugins are configured to work with the OCaml Language Server:

### Installation

* [Atom](https://github.com/reasonml-editor/atom-ide-reason)

* [Code](https://github.com/freebroccolo/vscode-reasonml)

* [Oni](https://github.com/bryphe/oni/wiki/Language-Support#reason-and-ocaml)

* [Sublime Text](https://github.com/reasonml-editor/sublime-reason) (requires server installation)

* [(Neo)Vim](https://github.com/reasonml-editor/vim-reason-plus) (requires server installation)

## Server

### Installation

Some clients (noted above) do not ship the server and require it to be installed
separately:

```
npm install -g ocaml-language-server
```

You also need to globally install [Merlin](https://github.com/ocaml/merlin), used by this project under the hood. Try https://github.com/reasonml/reason-cli or, if you're using [OPAM](https://opam.ocaml.org), `opam install merlin`. If you're using Reason with BuckleScript, make sure you're on the 4.02.3 ocaml switch and do `opam install merlin.2.5.4`.

### Launching

Manually launching the server should only be necessary if you are using a custom
configuration or an LSP client that is not already configured for the OCaml
Language Server. In that case, the server can be started with one of the
following commands:

```sh
ocaml-language-server --node-ipc          # communicate over the node IPC
ocaml-language-server --socket={number}   # communicate over a unix socket
ocaml-language-server --stdio             # communicate over stdio
```

## Contributing

Contributions are welcome and encouraged. Please see the following documents:

* [Code of Conduct](CODE_OF_CONDUCT.md)
* [Contributing](CONTRIBUTING.md)
