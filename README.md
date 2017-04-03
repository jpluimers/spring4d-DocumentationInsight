# spring4d-DocumentationInsight

[DevJet Documentation Insight](http://www.devjetsoftware.com/products/documentation-insight/) projects to generate [Spring4D](https://bitbucket.org/sglienke/spring4d) documentation from the [XML Documentation Comments](http://docwiki.embarcadero.com/RADStudio/en/XML_Documentation_Comments) using the [Delphi XE7](http://docwiki.embarcadero.com/RADStudio/XE7/en/Main_Page) Spring4D projects.

## Requirements

- [DevJet Documentation Insight](http://www.devjetsoftware.com/products/documentation-insight/) 
- A clone of the [spring4d repository](https://bitbucket.org/sglienke/spring4d.git) to be in the `spring4d` subdirectory.

## Branches

These project files matched the branches present in `spring4d` as of 20161202::

- `Documentation.develop.diproj`
- `Documentation.master.diproj`
- `Documentation.release-1.2.diproj`

## `index.html` boilerplate

There is an `index.html` file in the root of the repository that contains a boilerplate header and `iframe` pointing to `Html\index.htm`.

You can copy this file to each generated `Doc` directory so it is easier for users to select which kind of documentation they want to access. 

## Modifying the project files

Depending on the future names of [spring4d branches](https://bitbucket.org/sglienke/spring4d/branches/), you need to duplicate these files and change these settings (either directly in the XML, or through the Documentation Insight user interface):

The example below is for the `release/1.2` branch.

    ...
      <Copyright>Copyright (c) 2009-2016 Spring4D Team</Copyright>
    ...
        <FooterHtml>branch develop 20161202 - Copyright (c) 2009-2016 Spring4D Team &lt;a href="http://www.spring4d.org" target="_blank"&gt;www.spring4d.org&lt;/a&gt;. Powered by &lt;a href="http://www.devjetsoftware.com/products/documentation-insight/" target="_blank"&gt;Documentation Insight&lt;/a&gt;</FooterHtml>
    ...
      <Sources>
        <Source>.\Spring4D\Packages\DelphiXE7\Spring.Base.dpk</Source>
    ...
      </Sources>
    ...
          <OutputDirectory>output\release.20161202\Doc\Html</OutputDirectory>
    ...
          <OutputFileName>output\release.20161202\Doc\CHM\Spring4D.chm</OutputFileName>
    ...
          <OutputFileName>output\release.20161202\Doc\MSHelp2\Spring4D.HxS</OutputFileName>
    ...
          <OutputFileName>output\release.20161202\Doc\HM\Spring4D.hmxp</OutputFileName>
    ...

## Generating the documentation

For each branch you can generate the documentation:

1. check out a `spring4d` branch
2. open the corresponding `.diproj` file in Documentation Insight
3. generate the documentation
4. copy the `index.html` boilerplate to the `Doc` directory of the branch under `output`
5. upload from the corresponding sub-directory under `output` to your web-server

## What is (not) generated

Right now, only the `html`, `chm` and `hmxp` documentation is generated. To generate `HxS` files, I need to figure out what to install without any Visual Studio version present.

## Tips while generating

- Do not leave SourceTree open at all (even if auto-refresh is disabled, it steal eats CPU when files inside a repository are changed)
- Disable Everything, Windows Search and other indexing for the `output` folder
- Disable anti-virus software for the `output` folder

