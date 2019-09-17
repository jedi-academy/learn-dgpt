# Collaborative Workflow in Detail
COMP4711 - BCIT/Dongguan - Fall 2019

## Organization

- maintainer (CAPTAIN) needs to create an organization
- it will hold all team repos

## Team Repo

- created inside organization
- master & develop (default) branches; no more, ever
- 1 maintainer/admin
- optional collaborators, but set their permissions to read
- readme
- license
- this will be the **team** remote repository, sometimes referred to as **upstream**

## Forking

- each team member forks the team repo into their account
, applies to the captain too if they plan to contribute

## Cloning

- your repo gets cloned locally
- all you *need* is the develop branch, master is ok too
- this will be the **origin** remote repository
- add the **team** remote repository, for synching

## Feature Branches

- all work you do is in a feature branch, sometimes called a topic branch
- name it meaningfully, perhaps with implied namespaces (eg round1/adjective)
- you can have as many of these as you want, for different pieces of work in the same project
- work, work, git add, git commit
- committing: git commit -S -m "meaningful message"
- use meaningful commit messages
- when ready, git push (to your repo, origin)
- if changes, work, add, commit & push again
- once merged, or if abandoned, delete the branch locally & in your repo

## Synching

- whenever something is merged in **team**, your **origin** develop branch will be "behind"
- synch: checkout develop, fetch team develop, push origin develop
- now your feature branches (any in progress) are out of synch with your develop
- synch them: checkout topic branch, merge develop, fix conflicts if needed (update, add & commit)
- your **origin** develop branch should always be in synch with **team** develop

## Pull Requests

- once  you push a feature branch, visit your repo on github
- select the feature branch
- create a PR, against the team develop branch

## Handling PRs (Captain)

- review open PRs
- merge or comment on each; reject it if too flawed

## Release

- at the end of each round, in our case
- all work has been done & merged, right?
- work on github for now
- in develop branch, make PR for master branch
- merge it
- in releases tab, create new release **from master**, with suitable name & description

## Cleanup

- after each release, team members should delete all unused branches & synch their master & develop

