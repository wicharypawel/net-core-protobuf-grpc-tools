# Net Core Protocol Buffers with Grpc.Tools nuget

# This repository

This repository shows how to work with Protocol Buffer (*.proto) while using Grpc.Tools nuget package integration. The process of working with Protocol Buffer is as follow: define proto file, rebuild project, use generated files in code.

## Getting started

1. Download repository 
2. Download .Net SDK (in the moment of writing 3.1.101)
3. Open in VS 2019
4. Setup startup project & start debugging

## Tools

### Generate code from proto files (Configuration for .NET, .NET Core and Visual Studio)

Protocol buffers files (*.proto) can be compiled together with *.cs files as part of a consistent application building mechanism. All available cross-platform with the minimum configuration using a single NuGet package.

1. Create a new .NET Standard project
2. Add the `helloworld.proto` file
3. Install a NuGet package called `Google.Protobuf` - a package containing definitions used by protocol buffers
4. Install NuGet package named `Grpc.Tools` - despite it's name, the package supports both protocol buffers and gRPC,
5. Include *.proto file to the compilation by modifying the *.csproj file (see example below)

```
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>netstandard2.1</TargetFramework>
    </PropertyGroup>
    
    <ItemGroup>
        <PackageReference Include="Google.Protobuf" Version="3.11.3" />
        <PackageReference Include="Grpc.Tools" Version="2.27.0" PrivateAssets="all" />
    </ItemGroup>
    
    <ItemGroup>
        <Protobuf Include="helloworld.proto" />
    </ItemGroup>
</Project>
```

Building the project should generate language native protocol buffers files in `.\objobug\netstandard2.1`, so they will be available at any time during the programmer's work. The advantages of this are support for intellisense, static compilation and strong typing. The code will be updated transparently every time the `helloworld.proto` file is changed. 

## Sources

- https://www.nuget.org/packages/Grpc.Tools/
- https://docs.microsoft.com/en-us/aspnet/core/grpc/?view=aspnetcore-3.1#c-tooling-support-for-proto-files
- https://developers.google.com/protocol-buffers/
- https://developers.google.com/protocol-buffers/docs/overview
- https://developers.google.com/protocol-buffers/docs/tutorials
- https://developers.google.com/protocol-buffers/docs/csharptutorial
- https://developers.google.com/protocol-buffers/docs/proto3
- https://developers.google.com/protocol-buffers/docs/style
- https://developers.google.com/protocol-buffers/docs/techniques
