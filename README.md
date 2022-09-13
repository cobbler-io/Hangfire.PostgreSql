# Hangfire.PostgreSql.NodaTime

Forked from https://github.com/frankhommers/Hangfire.PostgreSql

This fork fixes the library to support NodaTime at the database connection level.

## Publishing to Github Packages (private)

```bash
dotnet pack -c Release --include-symbols

dotnet nuget push .\bin\Release\Hangfire.PostgreSql.NodaTime.1.6.4.2.nupkg --api-key <Github PAT> --source "github"
```
