# svg-provider

Svg convert provider for ImageMagick delegate(internal).



## install

Clone the project and install it.

```bash
> brew install aimingoo/repo/svg-provider

# OR
> git clone https://github.com/aimingoo/svg-provider
> install svg-provider/svg-provider /usr/local/bin/

# OR
> cp svg-provider/svg-provider /usr/local/bin/
> chmod +x /usr/local/bin/svg-provider
```



## usage

You can direct execute `svg-provider` in console without ImageMagick. A simple command line help for you:

```bash
> svg-provider --help
 Svg convert provider for ImageMagick delegate(internal)
 Usage:
	> svg-provider <commands>
	  commands: --help, --version, --install, --uninstall, --info
	> svg-provider <file.svg> options ...
	  support: rsvg-convert cairosvg svg2png wasvg inkscape svgexport
	  options:
	    --force='%s'                      # force use a converter
	    --export-png='%s'                 # string - output file
	    --export-dpi='%s'                 # format - xRes,yRes
	    --export-background='%s'          # format - #ff007f, or rgb(r%,g%,b%)
	    --export-background-opacity='%s'  # number - 0.0 .. 1, or 2 .. 255
 Version: 1.0.2
```

Or, use `--install` or `--uninstall` to (un)install the tool for ImageMagick internal delegate list, and check it:

```bash
# show internal delegate information
> svg-provider --info
  <delegate decode="svg:decode" stealth="True" command="&quot;inkscape&quot; ...

# install
> svg-provider --install

# OR, install and force to cairosvg
> svg-provider --install --force=cairosvg

# OR, uninstall
> svg-provider --uninstall
```



## why?

The utility replace ImageMagick's internal delegate for `msvg:` format type, and redirect internal convert (.svg to .png) to your special configuration.

Read these documents ([Chinese](https://aimingoo.github.io/1-1727.html)), if you want to know more.



## History

```
2017.10.04 v1.0.2 released, implement --(un)install and --info
2017.06.08 Initalization release
```