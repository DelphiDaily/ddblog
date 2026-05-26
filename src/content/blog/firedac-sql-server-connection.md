---
title: "Connecting Delphi to SQL Server with FireDAC"
description: "A simple FireDAC connection example for SQL Server applications built with Delphi."
pubDate: 2026-05-27
author: "Ali Yeşiloğlu"
tags: ["Delphi", "FireDAC", "SQL Server"]
draft: false
---

FireDAC is a practical choice for Delphi applications that work heavily with relational databases.

## Example connection setup

```pascal
FDConnection1.DriverName := 'MSSQL';
FDConnection1.Params.Values['Server'] := 'localhost';
FDConnection1.Params.Values['Database'] := 'ELAS_DEV';
FDConnection1.Params.Values['User_Name'] := 'sa';
FDConnection1.Params.Values['Password'] := 'your-password';
FDConnection1.Connected := True;
```

In a real application, keep credentials outside the source code and use configuration files or environment-specific settings.
