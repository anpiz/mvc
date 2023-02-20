# Notas

## Crear un proyecto

```
dotnet new mvc -o Mvc
```

## Correr la app

```
dotnet watch run
```

## Crear modelo

```
using System.ComponentModel.DataAnnotations;

namespace Mvc.Models;

public class Person
{
    public int Id { get; set; }
    public string? Name { get; set; }
    public string? LastName { get; set; }
}
```

## Paquetes a instalar

```
dotnet tool uninstall --global dotnet-aspnet-codegenerator
dotnet tool install --global dotnet-aspnet-codegenerator
dotnet tool uninstall --global dotnet-ef
dotnet tool install --global dotnet-ef
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SQLite
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```

## Armado de las páginas

```
export PATH=$HOME/.dotnet/tools:$PATH // Si en *nix
dotnet aspnet-codegenerator controller -name PeopleController -m Person -dc Mvc.Data.MvcContext --relativeFolderPath Controllers --useDefaultLayout --referenceScriptLibraries -sqlite
```

## Migración para crear la base de datos

```
dotnet ef migrations add InitialCreate
dotnet ef database update
```
