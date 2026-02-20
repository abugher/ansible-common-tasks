# Purpose

These tasks are used by various ansible roles.  This repo should be a submodule of each role repo.

# Efficiency

It is recommended to keep one local copy of this repo synced from any networked upstream repo and use that local cache as the upstream for each copy of this repo submoduled into a role repo.  That should avoid reundaant syncing over the network at the cost of one extra local copy of this repo.
