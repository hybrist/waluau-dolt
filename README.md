# waluau-dolt

Storage-only repository for the [beads](https://github.com/gastownhall/beads) issue
tracker used by [hybrist/waluau](https://github.com/hybrist/waluau).

There is no source code here. The issue database is a Dolt database that beads
pushes into non-branch refs (`refs/dolt/data`) plus the bookkeeping branch
`__dolt_remote_info__`. It lives in its own repository so those refs stay out of
the main repo, where CI and deployment providers mistake them for real branches.

Do not clone this by hand. From a `hybrist/waluau` checkout:

```bash
bd bootstrap --yes
```

`.beads/config.yaml` in the main repo points `sync.remote` here.
