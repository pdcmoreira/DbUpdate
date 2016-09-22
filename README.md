#SQLServer simple migration tool

## Getting Started

- Create a `Migrations` folder where you will put all of your incremental `.SQL` scripts
- Run DbUpdate (see below)

## How to run DbUpdate

- Open the project in Visual Studio
- Build
- Grab the `DbUpdate.exe` and put it wherever you want
- Open CMD and run the command `DbUpdate.exe <ConnectionString> <MigrationsPath>`

### Run it when your application server starts up

C# example:
```cs
private void RunMigrations()
{
  var migrationsFolder = @"Database\Migrations";
  
  var connectionString = Configuration.GetConnectionString("AppDatabase");
  var arguments = "\"" + connectionString + "\" \"" + migrationsFolder + "\"";
  
  System.Diagnostics.Process.Start("DbUpdate.exe", arguments).WaitForExit();
}
```
