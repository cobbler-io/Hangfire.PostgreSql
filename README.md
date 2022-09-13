# Hangfire.PostgreSql.NodaTime

Forked from https://github.com/frankhommers/Hangfire.PostgreSql

This fork fixes the library to support NodaTime at the database connection level. It is published to our private Github Packages repository as `Hangfire.PostgreSql.NodaTime`.

## Keeping this fork up to date with the upstream
```bash
git fetch upstream
git merge upstream/master

# Fix merge conflicts (if any) and commit
```

## Publishing to Github Packages (private)

```bash
dotnet build -c Release

.\build --target Pack --exclusive # Skips tests (they fail unless you have a local postgres DB set up for Hangfire integration tests)

# Output:
#   Successfully created package 'C:\Users\Nate\Documents\Code\Hangfire.PostgreSql\publish\Hangfire.PostgreSql.NodaTime.1.9.10.nupkg'.

dotnet nuget push .\publish\Hangfire.PostgreSql.NodaTime.1.9.10.nupkg --api-key <Github PAT> --source "github"
```

Note that GitTool.Version (used by the build process for this package) automatically bumps the version number of the package to `(latest git tag) + 1`. In the example above, the most recent git tag pulled from the upstream was `1.9.9`, so the package has the version `1.9.10`. This means our fork will always have a version 0.0.1 greater than the current official version.