# nixsysdeps

This is a repository of JSON files that map language's packages to [nixpkgs](https://github.com/nixos/nixpkgs) attrpaths.

The schema is:
```
{
  "<packagename>": {

    "deps": [
      "<nixpkgs attrpath>"
      ...
    ],

    "libdeps": [
      "<nixpkgs attrpath>"
      ...
    ]
  }
  ...
}
```

Either `deps` or `libdeps` may optionally be excluded. `deps` represents dependencies that need to be present at installation or runtime. `libdeps` represents dependencies that need to be placed on the LD_LIBRARY_PATH of the the language runtime for the package to work.

For now, only Python is supported.

# Contributing

Adding additional dependencies is a very welcome contribution!

To contribute:
1. edit one of the json files
2. run ./scripts/checks.sh to check your changes will pass continuous integration testing.
3. make a git commit and open a Pull Request on this GitHub project.
