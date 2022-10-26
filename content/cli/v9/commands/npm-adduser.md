---
title: npm-adduser
section: 1
description: Add a registry user account
github_repo: npm/cli
github_branch: latest
github_path: docs/lib/content/commands/npm-adduser.md
redirect_from:
  - /cli-documentation/v9/adduser
  - /cli-documentation/v9/cli-commands/adduser
  - /cli-documentation/v9/cli-commands/npm-adduser
  - /cli-documentation/v9/commands/adduser
  - /cli-documentation/v9/commands/npm-adduser
  - /cli-documentation/v9/npm-adduser
  - /cli/v9/adduser
  - /cli/v9/cli-commands/adduser
  - /cli/v9/cli-commands/npm-adduser
  - /cli/v9/commands/adduser
  - /cli/v9/npm-adduser
---

### Synopsis

```bash
npm adduser

alias: add-user
```

Note: This command is unaware of workspaces.

### Description

Create a new user in the specified registry, and save the credentials to
the `.npmrc` file. If no registry is specified, the default registry
will be used (see [`registry`](/cli/v9/using-npm/registry)).

When using `legacy` for your `auth-type`, the username, password, and
email are read in from prompts.

### Configuration

#### `registry`

* Default: "https://registry.npmjs.org/"
* Type: URL

The base URL of the npm registry.

#### `scope`

* Default: the scope of the current project, if any, or ""
* Type: String

Associate an operation with a scope for a scoped registry.

Useful when logging in to or out of a private registry:

```
# log in, linking the scope to the custom registry
npm login --scope=@mycorp --registry=https://registry.mycorp.com

# log out, removing the link and the auth token
npm logout --scope=@mycorp
```

This will cause `@mycorp` to be mapped to the registry for future
installation of packages specified according to the pattern
`@mycorp/package`.

This will also cause `npm init` to create a scoped package.

```
# accept all defaults, and create a package named "@foo/whatever",
# instead of just named "whatever"
npm init --scope=@foo --yes
```


#### `auth-type`

* Default: "web"
* Type: "legacy" or "web"

What authentication strategy to use with `login`.

### See Also

* [npm registry](/cli/v9/using-npm/registry)
* [npm config](/cli/v9/commands/npm-config)
* [npmrc](/cli/v9/configuring-npm/npmrc)
* [npm owner](/cli/v9/commands/npm-owner)
* [npm whoami](/cli/v9/commands/npm-whoami)
* [npm token](/cli/v9/commands/npm-token)
* [npm profile](/cli/v9/commands/npm-profile)