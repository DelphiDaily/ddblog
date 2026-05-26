---
title: "Connecting Delphi to SQL Server with FireDAC"
description: "A minimal FireDAC connection example for SQL Server projects."
pubDate: 2026-05-27
author: "Ali Yeşiloğlu"
tags: ["Delphi", "FireDAC", "SQL Server"]
draft: false
---

FireDAC is a practical database access layer for Delphi applications. A clean connection setup makes the rest of the data layer easier to maintain.

```pascal
uses
  FireDAC.Comp.Client,
  FireDAC.Stan.Def,
  FireDAC.Phys.MSSQL;

procedure ConfigureConnection(const AConnection: TFDConnection);
begin
  AConnection.Params.Clear;
  AConnection.Params.DriverID := 'MSSQL';
  AConnection.Params.Database := 'DATABASE_NAME';
  AConnection.Params.UserName := 'sa';
  AConnection.Params.Password := 'your-password';
  AConnection.Params.Values['Server'] := 'localhost';
  AConnection.LoginPrompt := False;
  AConnection.Connected := True;
end;
```

For production code, keep credentials outside the source code and centralize connection creation behind a small factory or service.

```sql
SELECT
  DB_NAME() AS DatabaseName,
  @@VERSION AS SqlServerVersion;
```
