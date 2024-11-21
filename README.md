# gh-sbom-debug

When both a package.json and package-lock.json are in a repo the generated SBOM incorrectly gives a message that "Exact versions could not be resolved for some packages. For more information: ...". This message is removed if you remove the package.json and keep only the package-lock.json file in the repo. Both the deterministic version and the non-deterministic version of the dependency are included in the generated SBOM when both files are present.

The Dependency graph UI (under Insights tab) seems to correctly show that a dependency version is "locked" (even when both package.json and package-lock.json are present) while the sbom does not.

Test Steps:
1. Add package.json
2. Generate SBOM 1
3. Add package-lock.json
4. Generate SBOM 2
5. Remove package.json
6. Generate SBOM 3