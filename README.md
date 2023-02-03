Author : Sajid Ali</br>
|Cloud Solution Architect|</br>
Published Feb 03, 2023
  

# Repository and Unit of Work Patterns in .NET Core

## What are the Repository and Unit of Work Patterns?

<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

<!--step0-->

According to the official MS Docs [(Designing the infrastructure persistence layer | Microsoft Docs)](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design), repositories are classes or components that encapsulate the logic required to access data sources. They include methods for common operations, providing better decoupling and maintainability.
The Unit of Work pattern is used to aggregate multiple operations into a single transaction. With this we ensure that either all operations succeed or fail as a single unit.

_Note that you can use the Repository pattern without using the Unit of Work pattern. :tada:!_



## Implementing the Repository and Unit of Work Patterns
<!--
  <<< Author notes: Start of the course >>>
  Include start button, a note about Actions minutes,
  and tell the learner why they should take the course.
  Each step should be wrapped in <details>/<summary>, with an `id` set.
  The start <details> should have `open` as well.
  Do not use quotes on the <details> tag attributes.
-->

<!--step0-->

The project uses Entity Framework Core as our O/RM. I suggest you read the official MS Docs [Overview of Entity Framework Core - EF Core | Microsoft Docs](https://learn.microsoft.com/en-us/ef/core/) for more information.

<b><i>One important thing to highlight here:</i></b>
  
According to the official MS Docs [(DbContext Class (System.Data.Entity) | Microsoft Docs)](https://learn.microsoft.com/en-us/dotnet/api/system.data.entity.dbcontext?view=entity-framework-6.2.0), the DbContext class is a combination of the Unit of Work and Repository patterns, where the DbContext is an abstraction of the Unit of Work pattern and a DbSet is an abstraction of the Repository pattern.

So, you don’t need to use any of these patterns in your code, if you wish. But it is a good approach to create an additional layer of abstraction over them if you don’t want your project to be tightly coupled to Entity Framework Core.


