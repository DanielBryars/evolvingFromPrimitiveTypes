# Evolving Away from Primitive Types

Supporting documentation and code examples for a .NET Oxford meetup talk on moving away from primitive types to create more type-safe C# code.

## Overview

This repository contains presentation materials and demonstration code for a talk about evolving from primitive types (strings, ints, GUIDs) to more strongly-typed domain models in C#. The talk demonstrates how using proper types can prevent common programming errors and make code more maintainable.

## Talk Details

**Presented at**: [.NET Oxford](https://www.dotnetoxford.com/)

**Meetup Group**: [.NET Oxford on Meetup](https://www.meetup.com/dotnetoxford/)

## Key Concepts

### The Problem with Primitives

Using primitive types for domain concepts leads to issues:
- **Parameter Confusion**: Easy to swap parameters of the same type
- **No Type Safety**: Compiler can't catch logical errors
- **Unclear Intent**: What does a `Guid` or `string` represent?
- **Runtime Errors**: Bugs only discovered during execution

### The Solution: Domain Types

Create specific types for domain concepts using C# records:

```csharp
// Instead of:
void ReleaseTheHounds(Guid tenantId, Guid packId) { }

// Use:
public record TenantId(Guid Value);
public record PackId(Guid Value);
void ReleaseTheHounds(TenantId tenantId, PackId packId) { }
```

## Benefits

- **Compile-Time Safety**: Type errors caught by compiler
- **Self-Documenting Code**: Types convey meaning
- **Refactoring Confidence**: Changes are safer
- **Domain-Driven Design**: Code matches business language
- **Prevent Logic Errors**: Can't accidentally swap parameters

## Code Examples

The repository includes demonstrations of:
- Identifying primitive types in C#
- Common pitfalls (parameter order mistakes)
- Record types for value objects
- Type-safe function signatures
- Strong typing for IDs (TenantId, PackId)

## Contents

- **Evolving Away from Primitive Types.pptx**: Full presentation slides
- **src/EvolvingAway/Program.cs**: Code demonstrations
- **evolvingFromPrimitiveTypes.sln**: Visual Studio solution

## Technologies

- **.NET / C#**: Modern C# features (records)
- **Visual Studio**: Development environment
- **C# 9.0+**: Record types and modern syntax

## Running the Examples

1. Open `evolvingFromPrimitiveTypes.sln` in Visual Studio
2. Build and run the solution
3. Observe compiler errors vs runtime errors
4. See demonstrations of type safety improvements

## Key Takeaways

1. **Primitive Obsession is an Anti-Pattern**: Overuse of primitives makes code fragile
2. **Records are Ideal for Value Objects**: Lightweight, immutable, value-based equality
3. **Type Safety Prevents Bugs**: Catch errors at compile time, not runtime
4. **Better Domain Modeling**: Code structure reflects business concepts
5. **Minimal Overhead**: Modern C# makes this pattern easy and performant

## C# Features Demonstrated

- **Record Types**: Immutable value objects
- **Primitive Type Detection**: `IsPrimitive` property
- **String Interpolation**: Modern string formatting
- **Nameof Operator**: Refactoring-safe string references

## Related Patterns

- **Value Objects** (Domain-Driven Design)
- **Strongly Typed IDs**
- **Primitive Obsession** (anti-pattern)
- **Type Safety**
- **Domain Modeling**

## Community

Join .NET Oxford for more talks and discussions:
- Website: https://www.dotnetoxford.com/
- Meetup: https://www.meetup.com/dotnetoxford/

## Status

Complete presentation with working code examples from the .NET Oxford talk.




