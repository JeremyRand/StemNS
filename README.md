
# Proposal 279

This is an implementation of the "Tor side" of Proposal 279 ("naming
layer api") so that actual naming plugins can be tested/prototyped
"now" without changing Tor.

StemNS is a fork of the original [TorNS](https://github.com/meejah/TorNS) by meejah, which is modified to use Stem instead of txtorcon.

# Using This

It will currently connect to a system tor on localhost:9051 or you can
change this to 9151 (in poc.py) to react a Tor Browser Bundle
instance.

This actually works and launches two example services, reached via:
<something>.<service>.onion where the two services are .pet.onion for
the ns_petname.py lookup (so try, e.g., "http://scihub.pet.onion" in
TBB).

The other one is .demo.onion and will always remap to txtorcon's
documentation hidden-service. So <anything>.demo.onion will redirect
you to txtorcon's documentation.

# Naming Implementations

 - "banana" does naming based on /etc/hosts: https://github.com/pickfire/banana
 - "dns-prop279" does naming based on DNS `TXT` records: https://github.com/namecoin/dns-prop279

# License

Code specific to StemNS, and the code StemNS inherits from TorNS, is licensed under the Unlicense (see `LICENSE`).  StemNS inherits some code from [OnioNS-client](https://github.com/Jesse-V/OnioNS-client), which is licensed under the Modified/New BSD License (see `LICENSE.OnioNS`).

This product is produced independently from the Tor® anonymity software and carries no guarantee from The Tor Project about quality, suitability or anything else.
