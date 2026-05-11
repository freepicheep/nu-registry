# nu-registry

An example registry for Nu modules and plugins

## Structure

The registry is git based and has a simple layout.

```
registry/
├── index/
│   ├── nu-salesforce/
│   │   └── package.toml
│   └── nu_plugin_semver/
│       └── package.toml
```

## Defining a Package

A package is defined in TOML and the `package.toml` is placed in a directory with the package's name. For example, if you package is called "nu-salesforce", place the `package.toml` defining your package in the `nu-salesforce` subdir in the index.

Versions of your package are added to the `versions` table. This is especially important for plugins so a package manager can identify which release to fetch for the declared `nu-version`.

```toml
[package]
name = "nu-salesforce"
description = "Query and update your Salesforce data with Nu"
type = "module"
license = "MIT"
authors = [
  { name = "Friedrich Stoltzfus", email = "friedrichstoltzfus@gmail.com" }
]
keywords = ["Salesforce", "API"]
repository = "https://github.com/freepicheep/nu-salesforce"

[[versions]]
version = "0.2.0"
git = "https://github.com/freepicheep/nu-salesforce"
tag = "v0.2.0"
nu-version = ">=0.110.0"
published = "2026-02-18"

[[versions]]
version = "0.3.0"
git = "https://github.com/freepicheep/nu-salesforce"
tag = "v0.3.0"
nu-version = ">=0.110.0"
published = "2026-02-20"

[[versions]]
version = "0.3.1"
git = "https://github.com/freepicheep/nu-salesforce"
tag = "v0.3.1"
nu-version = ">=0.110.0"
published = "2026-03-02"

[[versions]]
version = "0.3.2"
git = "https://github.com/freepicheep/nu-salesforce"
tag = "v0.3.2"
nu-version = ">=0.110.0"
published = "2026-04-09"
```
