# Addin packaging

The convention for Fody addin NuGet packages is as follows:

&#x1F4C1; build<br>
&#09; AddinName.Fody.props<br>
&#x1F4C1; lib<br>
&#09;&#x1F4C1; net452<br>
&#09;&#09; AddinName.dll<br>
&#09;&#09; AddinName.xml<br>
&#09;&#x1F4C1; netstandard2.0<br>
&#09;&#09; AddinName.dll<br>
&#09;&#09; AddinName.xml<br>
&#x1F4C1; netclassicweaver<br>
&#09; AddinName.Fody.dll<br>
&#09; AddinName.Fody.pdb<br>
&#09; AddinName.Fody.xcf<br>
&#x1F4C1; netstandardweaver<br>
&#09; AddinName.Fody.dll<br>
&#09; AddinName.Fody.pdb<br>
&#09; AddinName.Fody.xcf<br>


 * build/AddinName.Fody.props: Facilitates [addin discovery](addin-discovery.md) via an [props file included by NuGet](https://docs.microsoft.com/en-us/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).
 * lib: Contains the [Lib/Reference project](addin-development.md#Lib/Reference-project) for all [supported target frameworks](https://docs.microsoft.com/en-us/nuget/create-packages/supporting-multiple-target-frameworks).
 * netclassicweaver/netstandardweaver: Contains the [Weaver Project](addin-development.md#Weaver-Project) assemblies. Also contains the XCF file to [Supporting intellisense for FodyWeavers.xml](addin-development.md#Supporting-intellisense-for-FodyWeavers.xml).


## FodyPackaging NuGet Package

The [FodyPackaging NuGet Package](https://www.nuget.org/packages/FodyPackaging/) simplifies following the above convention.


### MSBuild props and targets

The below files are include as [MSBuild props and targets in a package](https://docs.microsoft.com/en-us/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).


#### FodyPackaging.props

snippet: FodyPackaging.props


#### FodyPackaging.targets

snippet: FodyPackaging.targets


### Weaver.props

Included in the consuming package to facilitate [addin discovery](addin-discovery.md).

snippet: Weaver.props

