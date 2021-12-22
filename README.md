# FreeBSD GitHub runner (self-hosted) quick/dirty howto.

1) on Github:

Go to 'Settings' -> 'Actions' -> Runners -> [New self-hosted runner]

Runner image: 'Linux'

Copy --token from Configure, e.g:  AAHCxxxOC


2) On FreeBSD host:

```
git clone https://github.com/ChristopherHX/github-act-runner.git --recursive
cd github-act-runner
git pull
git submodule update
go run . configure --url https://github.com/olevole/gh-action-sample --name srv-01 -l freebsd-14,cbsd-hoster --token AAHCxxxOC
```

( where 'https://github.com/olevole/gh-action-sample' - your GitHub project)

```
go run . run
```

Now Runner available in status page

![image](https://user-images.githubusercontent.com/926409/147156127-02580d10-c076-4763-8703-4ff0f7bf716d.png)


3) Create .github/workflows, e.g.: https://github.com/olevole/gh-action-sample/blob/main/.github/workflows/act.yml


Hint: there are many checkout methods available. Test and choose the one that suits you best. My example uses external checkout script.
