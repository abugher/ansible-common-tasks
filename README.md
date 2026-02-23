# Purpose

These tasks are used by various ansible roles.  This repo should be a submodule of each role repo.

# Usage

If you want to use one of these tasks in a role, include it in `tasks/main.yml` and set the required variables in `vars/main.yml`.

# Efficiency

It is recommended to keep one local copy of this repo synced from any networked upstream repo and use that local cache as the upstream for each copy of this repo submoduled into a role repo.  That should avoid reundaant syncing over the network at the cost of one extra local copy of this repo.

# BUGS

Reference to tasks can be a little confusing, between the shared tasks
directory and per-role task directories.  Ansible has an interesting search
order for inclusions, and I found that if a per-role task file has the same
name as a shared task file, it's possible for ansible to misinterpret the
relative path, find the wrong one, and even get stuck in a loop if the per-role
task calls the shared task.  For now, avoid using the same name between shared
and per-role task files.  This could use a more systematic solution, though.
