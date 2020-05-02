<!--
GENERATED FILE - DO NOT EDIT
This file was generated by [MarkdownSnippets](https://github.com/SimonCropp/MarkdownSnippets).
Source File: /readme.source.md
To change this file edit the source file and then run MarkdownSnippets.
-->

# <img src="/src/icon.png" height="30px"> Verify.ImageSharp

[![Build status](https://ci.appveyor.com/api/projects/status/o30f8u47l7vv5844?svg=true)](https://ci.appveyor.com/project/SimonCropp/Verify-ImageSharp)
[![NuGet Status](https://img.shields.io/nuget/v/Verify.ImageSharp.svg)](https://www.nuget.org/packages/Verify.ImageSharp/)

Extends [Verify](https://github.com/SimonCropp/Verify) to allow verification of documents via [ImageSharp](https://github.com/SixLabors/ImageSharp).

Support is available via a [Tidelift Subscription](https://tidelift.com/subscription/pkg/nuget-verify.imagesharp?utm_source=nuget-verify.imagesharp&utm_medium=referral&utm_campaign=enterprise).

<!-- toc -->
## Contents

  * [Usage](#usage)
    * [Verify a file](#verify-a-file)
    * [Verify an Image](#verify-an-image)
  * [File Samples](#file-samples)
  * [Security contact information](#security-contact-information)<!-- endtoc -->


## NuGet package

https://nuget.org/packages/Verify.ImageSharp/


## Usage

Given a test with the following definition:

<!-- snippet: TestDefinition -->
<a id='snippet-testdefinition'/></a>
```cs
public class Samples :
    VerifyBase
{
    public Samples(ITestOutputHelper output) :
        base(output)
    {
    }

    static Samples()
    {
        VerifyImageSharp.Initialize();
    }
```
<sup><a href='/src/Tests/Samples.cs#L9-L22' title='File snippet `testdefinition` was extracted from'>snippet source</a> | <a href='#snippet-testdefinition' title='Navigate to start of snippet `testdefinition`'>anchor</a></sup>
<!-- endsnippet -->


### Verify a file

<!-- snippet: VerifyImageFile -->
<a id='snippet-verifyimagefile'/></a>
```cs
[Fact]
public Task VerifyImageFile()
{
    return VerifyFile("sample.jpg");
}
```
<sup><a href='/src/Tests/Samples.cs#L24-L32' title='File snippet `verifyimagefile` was extracted from'>snippet source</a> | <a href='#snippet-verifyimagefile' title='Navigate to start of snippet `verifyimagefile`'>anchor</a></sup>
<!-- endsnippet -->

Two files are produced


#### Info file:

Samples.VerifyImageFile.info.verified.txt

<!-- snippet: Samples.VerifyImageFile.info.verified.txt -->
<a id='snippet-Samples.VerifyImageFile.info.verified.txt'/></a>
```txt
{
  Width: 1599,
  Height: 1066,
  HorizontalResolution: 1.0,
  VerticalResolution: 1.0
}
```
<sup><a href='/src/Tests/Samples.VerifyImageFile.info.verified.txt#L1-L6' title='File snippet `Samples.VerifyImageFile.info.verified.txt` was extracted from'>snippet source</a> | <a href='#snippet-Samples.VerifyImageFile.info.verified.txt' title='Navigate to start of snippet `Samples.VerifyImageFile.info.verified.txt`'>anchor</a></sup>
<!-- endsnippet -->


#### Image file:

Samples.VerifyImageFile.verified.jpg

<img src="/src/Tests/Samples.VerifyImageFile.verified.jpg" width="200px">


### Verify an Image

An instance if an `Image` can be verified using the following:

<!-- snippet: VerifyImage -->
<a id='snippet-verifyimage'/></a>
```cs
[Fact]
public Task VerifyImage()
{
    var image = new Image<Rgba32>(11, 11)
    {
        [5, 5] = Rgba32.ParseHex("#0000FF")
    };
    var settings = new VerifySettings();
    settings.UseExtension("png");
    return Verify(image, settings);
}
```
<sup><a href='/src/Tests/Samples.cs#L34-L47' title='File snippet `verifyimage` was extracted from'>snippet source</a> | <a href='#snippet-verifyimage' title='Navigate to start of snippet `verifyimage`'>anchor</a></sup>
<!-- endsnippet -->


## File Samples

http://file-examples.com/


## Security contact information

To report a security vulnerability, use the [Tidelift security contact](https://tidelift.com/security). Tidelift will coordinate the fix and disclosure.


## Icon

[Swirl](https://thenounproject.com/term/pattern/2719636/) designed by [B�CK, RU](https://thenounproject.com/titaniclast/) from [The Noun Project](https://thenounproject.com/creativepriyanka).
