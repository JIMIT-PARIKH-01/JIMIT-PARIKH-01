# Tool access — how it works

Most of my tools are **public**: clone, download the ZIP, or `pip install` them
directly (see each repo's *Download & Install* section). No permission needed.

A few tools may be **private**. A web page cannot securely serve or unlock
private code — **GitHub's own permissions are the real gate.** So access always
flows through GitHub granting your account read access:

```
you request  ->  owner approves  ->  GitHub adds you as a collaborator  ->  you can clone/download
```

## For someone requesting access
1. Open an [access request issue](https://github.com/JIMIT-PARIKH-01/JIMIT-PARIKH-01/issues/new?template=tool-access-request.md)
   (or reach me on [LinkedIn](https://www.linkedin.com/in/jimit-devangkumar-parikh/)).
2. Include **which tool** and your **GitHub username**.
3. Once approved you'll get a GitHub invite; accept it, then clone/download the
   repo with your own account.

## For the owner (me) — granting access
1. Review the request and the stated use.
2. On the private repo: **Settings → Collaborators → Add people** → enter their
   GitHub username → pick **Read**.
   *(CLI: `gh api -X PUT repos/JIMIT-PARIKH-01/<repo>/collaborators/<user> -f permission=pull`)*
3. Comment on the issue that access is granted, and close it.

## Revoking access
Remove them from **Settings → Collaborators** (or
`gh api -X DELETE repos/JIMIT-PARIKH-01/<repo>/collaborators/<user>`). Their
ability to pull the repo ends immediately.

> Security note: granting collaborator **Read** lets someone clone and download,
> but not push. Never share tokens or paste credentials to grant access — use the
> collaborator system so access is auditable and revocable.
