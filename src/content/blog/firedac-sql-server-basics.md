---
title: "Connecting Delphi to SQL Server with FireDAC"
description: "A clean starting point for using FireDAC with SQL Server in Delphi applications."
pubDate: 2026-05-25
author: "Ali Yeşiloğlu"
tags: ["Delphi", "FireDAC", "SQL Server", "Database"]
draft: false
---

FireDAC is one of the most common choices for database access in modern Delphi applications. For SQL Server projects, a clean connection layer makes the rest of the application easier to test, maintain, and evolve.

## Basic connection idea

A typical setup uses a `TFDConnection`, one or more `TFDQuery` components, and transactions around write operations.

```pascal
procedure TDatabaseModule.Connect;
begin
  FDConnection1.Params.DriverID := 'MSSQL';
  FDConnection1.Params.Database := 'DATABASE_NAME';
  FDConnection1.Params.UserName := 'sa';
  FDConnection1.Connected := True;
end;
```

Avoid scattering connection strings across forms. Keep connection setup in one place, then expose clear methods for the application layer.

## Keep SQL readable

Delphi can hide database details behind components, but your SQL still deserves care. Use meaningful aliases, predictable parameters, and clear transaction boundaries.
