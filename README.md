# svg-provider

Svg convert provider for ImageMagick delegate(internal).



## install

Clone the project and install it.

```bash
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
###############################################################################
 Svg convert provider for ImageMagick delegate(internal)
 Version: 1.01
 Usage:
	> svg-provider <commands>
	  commands: --help, --install
	> svg-provider <file.svg>  options ...
	  support: rsvg-convert cairosvg svg2png wasvg inkscape svgexport
	  options:
	    --force='%s'                      # force use a converter
	    --export-png='%s'                 # string - output file
	    --export-dpi='%s'                 # format - xRes,yRes
	    --export-background='%s'          # format - #ff007f, or rgb(r%,g%,b%)
	    --export-background-opacity='%s'  # number - 0.0 .. 1, or 2 .. 255
###############################################################################
```



Or, use `svg-provider --install` to install the tool into ImageMagick internal delegate list, and check it:

```bash
> convert -list delegate | grep 'svg:decode'
 svg:decode =>          "svg-provider' '%s' ...
```



## why?

The utility replace ImageMagick's  internal delegate for `msvg:` format type, and redirect internal convert (.svg to .png) to your special configuration.

Read these documents ([Chinese](https://aimingoo.github.io/1-1727.html)), if you want to know more.
