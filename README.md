# cbsd-freebsd-bases

1) on Github:

Go to 'Settings' -> 'Actions' -> Runners -> [New self-hosted runner]

Runner image: 'Linux'

Copy --token from Configure, e.g:  AAHCxxxOC


2) On FreeBSD host:

git clone https://github.com/ChristopherHX/github-act-runner.git --recursive
cd github-act-runner
git pull
git submodule update
go run . configure --url https://github.com/olevole/gh-action-sample --name srv-01 -l freebsd-14,cbsd-hoster --token AAHCxxxOC

( where 'https://github.com/olevole/gh-action-sample' - your GitHub project)

go run . run


Now Runner available in status page


3) Create .github/workflows, e.g.: https://github.com/olevole/gh-action-sample/blob/main/.github/workflows/act.yml


