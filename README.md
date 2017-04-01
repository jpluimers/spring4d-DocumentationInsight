# spring4d-DocumentationInsight

Requires:

- [DevJet Documentation Insight](http://www.devjetsoftware.com/products/documentation-insight/) projects to generate [Spring4D](https://bitbucket.org/sglienke/spring4d) documentation using [Delphi XE7](http://docwiki.embarcadero.com/RADStudio/XE7/en/Main_Page)
- A clone of the [spring4d repository](https://bitbucket.org/sglienke/spring4d.git) to be in the `spring4d` subdirectory.

These project files matched the branches present in `spring4d` as of 20161202::

- `Documentation.develop.diproj`
- `Documentation.master.diproj`
- `Documentation.release-1.2.diproj`

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

For each branch you can generate the documentation:

1. check out a `spring4d` branch
2. open the corresponding `.diproj` file
3. generate the documentation
4. upload from the corresponding sub-directory under `output`

Right now, only the `html`, `chm` and `hmxp` documentation is generated. To generate `HxS` files, I need to figure out what to install without any Visual Studio version present.

