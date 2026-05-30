---
title: "Using Interfaces in Object Pascal"
description: "How interfaces can help organize Delphi code without turning a business application into an abstract maze."
pubDate: 2026-05-24
author: "DD"
tags: ["Object Pascal", "Interfaces", "Architecture"]
draft: false
---

Interfaces are useful when they describe a real contract in your application. They are less useful when they are added only to decorate simple code with architectural fog.

## A small contract

```delphi
type
  IShipmentCalculator = interface
    ['{9A9BBCA7-88C3-4A8C-91C3-2EF8C94E1A20}']
    function CalculateStorageFee(const AWeight: Double; const ADays: Integer): Currency;
  end;
```

This is useful because the rest of the application can depend on the calculation behavior without knowing the implementation details.

## Use interfaces where they clarify ownership

Good places for interfaces include services, strategies, gateways, calculators, repositories, and adapters. Poor places include every tiny class by default.

The goal is not to worship abstraction. The goal is to make change less painful.
