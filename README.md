# nu-registry

An example registry for Nu modules and plugins

## Structure

The registry is git based and has a simple layout.

```
registry/
├── index/
│   ├── nu-salesforce/
│   │   └── package.nuon
│   └── nu_plugin_semver/
│       └── package.nuon
```

## Defining a Package

A package is defined in `nuon` and the `package.nuon` is placed in a directory with the package's name. For example, if you package is called "nu-salesforce", place the `package.nuon` defining your package in the `nu-salesforce` subdir in the index.

Versions of your package are added to the `versions` table. This is especially important for plugins so a package manager can identify which release to fetch for the declared `nu-version`.

```nuon
{
    package: {
        name: nu-salesforce
        description: "Query and update your Salesforce data with Nu"
        type: module
        license: MIT
        authors: [
            [name email];
            ["Friedrich Stoltzfus" "friedrichstoltzfus@gmail.com"]
        ]
        keywords: [
            Salesforce
            API
        ]
        repository: "https://github.com/freepicheep/nu-salesforce"
    }
    versions: [
        [version git tag nu-version published];
        ["0.2.0" "https://github.com/freepicheep/nu-salesforce" "v0.2.0" ">=0.110.0" "2026-02-18"]
        ["0.3.0" "https://github.com/freepicheep/nu-salesforce" "v0.3.0" ">=0.110.0" "2026-02-20"]
        ["0.3.1" "https://github.com/freepicheep/nu-salesforce" "v0.3.1" ">=0.110.0" "2026-03-02"]
        ["0.3.2" "https://github.com/freepicheep/nu-salesforce" "v0.3.2" ">=0.110.0" "2026-04-09"]
    ]
}
```
