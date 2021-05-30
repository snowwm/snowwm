promise-meta

[meta]
- possible names
	- Singula
- motto?
- principles
	- semantics everywhere!
	- AI- or bot-friendly
	- controllable: close to git
	- stateless: as much as possible; all state can be inspected & manipulated
	- transparent, determinated
	- isolation, yet open for collaboration
	- maximally mirror physical world (https://www.inkandswitch.com/muse-studio-for-ideas.html)
 - practices
	- always reserve prefixes (keywords & identifiers)
	- always explicitly specify versions

[connect anything with anything]
- universal routing of data/command streams
	- onion
	- mux
	- tee/tap
- automatic networks
  - instant creation of a local network
  - granting privileges to authorities (using PKI)
    - example: switch phone to quiet mode in the theatre
  - (de)duplication of services
    - switch between router- and local-based services

[interop]
- small composable tools!

- well-known entities
		- https://schema.org/
    	- a registry of well-known names for each entity type
    	- community-maintained, yet centralized (like npm, Wikipedia)
    	- defines only behavior, not implementation
    	- parameterization
    	- namespaces
    	- example
		@none - standard namespace
		aaa/bbb - local
		/example/com/bbb - namespaced

- separation of intent and interface
  - example: iptables and nftables share the same intent; an application may understand one or both interfaces

- unified format for structured text

- installing and connecting a library in different language via IPC should be as easy as importing a native one

[human interface]
- maximally straightforward mappings between human- and machine-readable objects or (trans)actions

- a metaphor of programs being bots (guests, workers in a house) (https://www.inkandswitch.com/end-user-programming.html#bots)

- first-class _semantics_
  - every object or (trans)action has: some environment, purpose, why it was done _that_ way, etc.
  - example: why the package was installed

- universal grouping
    - interchangeable groups and objects
    - hierarchy, inheritance
    - example: trip luggage list may have groups of items and groups of destinations, with filtering based on these


promise-os

[meta:resources]
- `asana:fs`: https://invent.life/blog/on-organizing-projects-and-files/

[ui]
- hardware LED indicating interaction with the system

[fs]
- read-only hash-addressed object storage
- tags
    - example: ::mime(text) ::project(promise-fs) ::type(source-file)
    - per-user tags
- well-known tags
    - see promise-meta#well-known
- queries
    - basically,  a set of tags
- mounts
    - queries can be mounted in a traditional tree shape
    - can inherit parent's props or start a new context (essentially a symlink)


promise-components

[ui]
- intermediate language:
  - describes data and UI
  - uses abstract widgets
  - makes minimal assumptions about the L&F or functionality of actual widgets

- style language

- widgets toolkit

[shell]
see perl

[connectivity]

[permissions]

[scheduler]

[metadata]
unify:
- filename
- file attributes
- MIME type
- symlinks
- media attributes (e.g. MP3 tags)
- content hash
- encryption/signatures
peel and stack metadata containers
layer sharing
semantic copy/move/edit
