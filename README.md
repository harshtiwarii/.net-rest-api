# .net-rest-api
builded a dotnet 5 web api project from scratch
Introduction to .NET
16/11/2020
14 minutes to read






+7
.NET is a free, open-source development platform for building many kinds of apps, such as:

Web apps, web APIs, and microservices
Serverless functions in the cloud
Cloud native apps
Mobile apps
Desktop apps
Windows WPF
Windows Forms
Universal Windows Platform (UWP)
Games
Internet of Things (IoT)
Machine learning
Console apps
Windows services
Share functionality among different apps and app types by using class libraries.

With .NET, your code and project files look and feel the same no matter which type of app you're building. You have access to the same runtime, API, and language capabilities with each app.

Cross platform
You can create .NET apps for many operating systems, including:

Windows
macOS
Linux
Android
iOS
tvOS
watchOS
Supported processor architectures include:

x64
x86
ARM32
ARM64
.NET lets you use platform-specific capabilities, such as operating system APIs. Examples are Windows Forms and WPF on Windows and the native bindings to each mobile platform from Xamarin.

For more information, see Supported OS lifecycle policy and .NET RID Catalog.

Open source
.NET is open source, using MIT and Apache 2 licenses. .NET is a project of the .NET Foundation.

For more information, see the list of project repositories on GitHub.com.

Support
.NET is supported by Microsoft on Windows, macOS, and Linux. It's updated regularly for security and quality, on the second Tuesday of each month.

.NET binary distributions from Microsoft are built and tested on Microsoft-maintained servers in Azure and follow Microsoft engineering and security practices.

Red Hat supports .NET on Red Hat Enterprise Linux (RHEL). Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.

Tizen supports .NET on Tizen platforms.

For more information, see Releases and support for .NET Core and .NET 5.

Tools and productivity
.NET gives you a choice of languages, integrated development environments (IDEs), and other tools.

Programming languages
.NET supports three programming languages:

C#

C# (pronounced "See Sharp") is a modern, object-oriented, and type-safe programming language. C# has its roots in the C family of languages and will be immediately familiar to C, C++, Java, and JavaScript programmers.

F#

The F# language supports functional, object-oriented, and imperative programming models.

Visual Basic

Among the .NET languages, the syntax of Visual Basic is the closest to ordinary human language, which can make it easier to learn. Unlike C# and F#, for which Microsoft is actively developing new features, the Visual Basic language is stable. Visual Basic isn't supported for web apps, but it is supported for web APIs.

Here are some of the capabilities that .NET languages support:

Type safety
Type inference - C#, F#, Visual Basic
Generic types
Delegates
Lambdas
Events
Exceptions
Attributes
Asynchronous code
Parallel programming
Code analyzers
IDEs
The integrated development environments for .NET include:

Visual Studio

Runs on Windows only. Has extensive built-in functionality designed to work with .NET. The Community edition is free for students, open-source contributors, and individuals.

Visual Studio Code

Runs on Windows, macOS, and Linux. Free and open source. Extensions are available for working with .NET languages.

Visual Studio for Mac

Runs on macOS only. For developing .NET apps and games for iOS, Android, and web.

GitHub Codespaces

An online Visual Studio Code environment, currently in beta.

SDK and runtimes
The .NET SDK is a set of libraries and tools for developing and running .NET applications.

When you download .NET, you can choose the SDK or a runtime, such as the .NET runtime or the ASP.NET Core runtime. Install a runtime on a machine that you want to prepare for running .NET apps. Install the SDK on a machine that you want to use for development. When you download the SDK, you automatically get the runtimes with it.

The SDK download includes the following components:

The .NET CLI. Command-line tools that you can use for local development and continuous integration scripts.
The dotnet driver. A CLI command that runs framework-dependent apps.
The Roslyn and F# programming language compilers.
The MSBuild build engine.
The .NET runtime. Provides a type system, assembly loading, a garbage collector, native interop, and other basic services.
Runtime libraries. Provides primitive data types and fundamental utilities.
The ASP.NET Core runtime. Provides basic services for internet-connected apps, such as web apps, IoT apps, and mobile backends.
The desktop runtime. Provides basic services for Windows desktop apps, including Windows Forms and WPF.
The runtime download includes the following components:

Optionally, the desktop or ASP.NET Core runtime.
The .NET runtime. Provides a type system, assembly loading, a garbage collector, native interop, and other basic services.
Runtime libraries. Provides primitive data types and fundamental utilities.
The dotnet driver. A CLI command that runs framework-dependent apps.
For more information, see the following resources:

.NET SDK overview
.NET CLI overview
dotnet command
Project system and MSBuild
A .NET app is built from source code by using MSBuild. A project file (.csproj, .fsproj, or .vbproj) specifies targets and associated tasks that are responsible for compiling, packing, and publishing code. There are SDK identifiers that refer to standard collections of targets and tasks. The use of these identifiers helps keep project files small and easy to work with. For example, here is a project file for a console app:

XML

Copy
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
And here's one for a web app:

XML

Copy
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
In these examples, the Sdk attribute of the Project element specifies a set of MSBuild targets and tasks that build the project. The TargetFramework element specifies the .NET version that the app depends on. You can edit the project file to add additional targets and tasks specific to the project.

For more information, see .NET project SDK overview and Target frameworks.

CI/CD
MSBuild and the .NET CLI can be used with various continuous integration tools and environments, such as:

GitHub Actions
Azure DevOps
CAKE
FAKE
For more information, see Using .NET SDK and tools in Continuous Integration (CI)

NuGet
NuGet is an open-source package manager designed for .NET. A NuGet package is a .zip file with the .nupkg extension that contains compiled code (DLLs), other files related to that code, and a descriptive manifest that includes information like the package's version number. Developers with code to share create packages and publish them to nuget.org or a private host. Developers who want to use shared code add a package to their project and can then call the API exposed by the package in their project code.

For more information, see NuGet documentation.

.NET Interactive
.NET Interactive is a group of CLI tools and APIs that enable users to create interactive experiences across the web, markdown, and notebooks.

For more information, see the following resources:

.NET In-Browser Tutorial
Using .NET notebooks with Jupyter on your machine
.NET Interactive documentation
Execution models
.NET apps run managed code in a runtime environment known as the Common Language Runtime (CLR).

CLR
The .NET CLR is a cross-platform runtime that includes support for Windows, macOS, and Linux. The CLR handles memory allocation and management. The CLR is also a virtual machine that not only executes apps but also generates and compiles code using a just-in-time (JIT) compiler.

For more information, see Common Language Runtime (CLR) overview.

JIT compiler and IL
Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL). When an app runs, the JIT compiler translates IL to machine code that the processor understands. JIT compilation happens on the same machine that the code is going to run on.

Since JIT compilation occurs during execution of the application, the compilation time is part of the run time. Therefore, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce. But a JIT compiler knows the actual hardware and can free developers from having to ship different implementations for different platforms.

The .NET JIT compiler can do tiered compilation, which means it can recompile individual methods at run time. This feature lets it compile quickly while still being able to produce a highly tuned version of the code for frequently used methods.

For more information, see Managed execution process and Tiered compilation.

AOT compiler
The default experience for most .NET workloads is the JIT compiler, but .NET offers two forms of ahead-of-time (AOT) compilation:

Some scenarios require 100% AOT compilation. An example is iOS.
In other scenarios, most of an app's code is AOT-compiled but some is JIT-compiled. Some code patterns aren't friendly to AOT (like generics). An example of this form of AOT compilation is the ready-to-run publish option. This form of AOT offers the benefits of AOT without its drawbacks.
Automatic memory management
The garbage collector (GC) manages the allocation and release of memory for applications. Each time your code creates a new object, the CLR allocates memory for the object from the managed heap. As long as address space is available in the managed heap, the runtime continues to allocate space for new objects. When not enough free address space remains, the GC checks for objects in the managed heap that are no longer being used by the application. It then reclaims that memory.

The GC is one of the CLR services that help ensure memory safety. A program is memory safe if it accesses only allocated memory. For instance, the runtime ensures that an app doesn't access unallocated memory beyond the bounds of an array.

For more information, see Automatic memory management and Fundamentals of garbage collection.

Working with unmanaged resources
Sometimes code needs to reference unmanaged resources. Unmanaged resources are resources that aren't automatically maintained by the .NET runtime. For example, a file handle is an unmanaged resource. A FileStream object is a managed object, but it references a file handle, which is unmanaged. When you're done using the FileStream, you need to explicitly release the file handle.

In .NET, objects that reference unmanaged resources implement the IDisposable interface. When you're done using the object, you call the object's Dispose() method, which is responsible for releasing any unmanaged resources. The .NET languages provide a convenient using statement (C#, F#, VB) that ensures the Dispose method is called.

For more information, see Cleaning up unmanaged resources.

Deployment models
.NET apps can be published in two different modes:

Publishing an app as self-contained produces an executable file that includes the .NET runtime and libraries, and the application and its dependencies. Users of the application can run it on a machine that doesn't have the .NET runtime installed. Self-contained apps are platform-specific, and they can optionally be published using a form of AOT compilation.

Publishing an app as framework-dependent produces an executable file and binary files (.dll files) that include only the application itself and its dependencies. Users of the application have to separately install the .NET runtime. The executable file is platform-specific, but the .dll files of framework-dependent applications are cross-platform.

You can install multiple versions of the runtime side by side to run framework-dependent apps that target different versions of the runtime. For more information, see Target frameworks.

Executables are produced for specific target platforms, which you specify with a runtime identifier (RID).

For more information, see .NET application publishing overview and Introduction to .NET and Docker.

Runtime libraries
.NET has an expansive standard set of class libraries, known as runtime libraries, framework libraries, or the base class library (BCL). These libraries provide implementations for many general-purpose and workload-specific types and utility functionality.

Here are some examples of types defined in the .NET runtime libraries:

Primitive types, such as System.Boolean and System.Int32.
Collections, such as System.Collections.Generic.List<T> and System.Collections.Generic.Dictionary<TKey,TValue>.
Data types, such as System.Data.DataSet and System.Data.DataTable.
Network utility types, such as System.Net.Http.HttpClient.
File and stream I/O utility types, such as System.IO.FileStream and System.IO.TextWriter.
Serialization utility types, such as System.Text.Json.JsonSerializer and System.Xml.Serialization.XmlSerializer.
High-performance types, such as System.Span<T>, System.Numerics.Vector, and Pipelines.
For more information, see the Runtime libraries overview. The source code for the libraries is in the GitHub dotnet/runtime repository.

Extensions to the runtime libraries
Libraries for some commonly used application functionality aren't included in the runtime libraries but are made available in NuGet packages, such as the following:

EXTENSIONS TO THE RUNTIME LIBRARIES
NuGet package	Documentation
Microsoft.Extensions.Hosting	Application lifetime management (Generic Host)
Microsoft.Extensions.DependencyInjection	Dependency injection (DI)
Microsoft.Extensions.Configuration	Configuration
Microsoft.Extensions.Logging	Logging
Microsoft.Extensions.Options	Options pattern
For more information, see the dotnet/extensions repository on GitHub.

Data access
.NET provides an Object/Relational Mapper (ORM) and a way to write SQL queries in code.

Entity Framework Core
Entity Framework (EF) Core is an open source and cross-platform data-access technology that can serve as an ORM. EF Core lets you work with a database by referring to .NET objects in code. It reduces the amount of data-access code you would otherwise need to write and test. EF Core supports many database engines.

For more information, see Entity Framework Core and Database Providers.

LINQ
Language-integrated query (LINQ) lets you write declarative code for operating on data. The data can be in many forms (such as in-memory objects, a SQL database, or an XML document), but the LINQ code you write typically doesn't differ by data source.

For more information, see LINQ (Language Integrated Query) overview.

.NET terminology
To understand .NET documentation, it can help to know how the usage of some terms has changed over time.

.NET Core and .NET 5
In 2002, Microsoft released .NET Framework, a development platform for creating Windows apps. Today .NET Framework is at version 4.8 and is still supported by Microsoft.

In 2014, Microsoft began writing a cross-platform, open-source successor to .NET Framework. This new implementation of .NET was named .NET Core until it reached version 3.1. The next version after .NET Core 3.1 is .NET 5.0. Version number 4 was skipped to avoid confusion between this implementation of .NET and .NET Framework 4.8. The name "Core" was dropped to make clear that this is now the main implementation of .NET.

This article is about .NET 5, but much of the documentation for .NET 5 still has references to ".NET Core" or ".NET Framework". In addition, "Core" remains in the names ASP.NET Core and Entity Framework Core.

The documentation also refers to .NET Standard. .NET Standard is an API specification that lets you develop class libraries for multiple implementations of .NET.

For more information, see .NET architectural components.

Overloaded terms
Some of the terminology for .NET can be confusing because the same word is used in different ways in different contexts. Here are a few of the more prominent instances:

runtime

TABLE 2
Context	"runtime" meaning
Common Language Runtime (CLR)	The execution environment for a managed program. The OS is part of the runtime environment but isn't part of the .NET runtime.
.NET runtime on the .NET download page	The CLR and runtime libraries, which together provide support for running framework-dependent apps. The page also offers runtime choices for ASP.NET Core server apps and Windows desktop apps.
Runtime Identifier (RID)	The OS platform and CPU architecture that a .NET app runs on. For example: Windows x64, Linux x64.
framework

TABLE 3
Context	"framework" meaning
.NET Framework	The original, Windows-only implementation of .NET. "Framework" is capitalized.
target framework	The collection of APIs that a .NET app or library relies on. Examples: .NET Core 3.1, .NET Standard 2.0
Target Framework Moniker (TFM)	A TFM is a standardized token format for specifying the target framework of a .NET app or library. Example: net462 for .NET Framework 4.6.2.
framework-dependent app	An app that can only run on a machine where you've installed the runtime from the .NET download page. "Framework" in this usage is the same thing as the "runtime" that you download from the .NET download page.
framework libraries	Sometimes used as a synonym for runtime libraries.
SDK

TABLE 4
Context	"SDK" meaning
SDK on the .NET download page	A collection of tools and libraries that you download and install to develop and run .NET apps. Includes the CLI, MSBuild, the .NET runtime, and other components.
SDK-style project	A set of MSBuild targets and tasks that specifies how to build a project for a particular app type. The SDK in this sense is specified by using the Sdk attribute of the Project element in a project file.
platform

TABLE 5
Context	"platform" meaning
cross platform	In this term, "platform" means an operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.
.NET platform	Usage varies. The reference may be to one implementation of .NET (such as .NET Framework or .NET 5) or to an overarching concept of .NET including all implementations.
For more information about .NET terminology, see the .NET glossary.

Advanced scenarios
The following sections explain some capabilities of .NET that are useful in advanced scenarios.

Native interop
Every operating system includes an application programming interface (API) that provides system services. .NET provides several ways to call those APIs.

The main way to interoperate with native APIs is via "platform invoke" or P/Invoke for short. P/Invoke is supported across Linux and Windows platforms. A Windows-only way of interoperating is known as "COM interop," which works with COM components in managed code. It's built on top of the P/Invoke infrastructure, but it works in subtly different ways.

For more information, see Native interoperability.

Unsafe code
Depending on language support, the CLR lets you access native memory and do pointer arithmetic via unsafe code. These operations are needed for certain algorithms and system interoperability. Although powerful, use of unsafe code is discouraged unless it's necessary to interoperate with system APIs or implement the most efficient algorithm. Unsafe code may not execute the same way in different environments and also loses the benefits of a garbage collector and type safety. It's recommended to confine and centralize unsafe code as much as possible and test that code thoroughly.
