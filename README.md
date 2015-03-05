Theming ownCloud
---

### This is a repository for a demonstration ownCloud theme

ownCloud provides the ability to customize its look and feel without the need
to patch the source code. This functionality is known as Theming.

This document will first discuss the “How-to” of basic theming then go into an example on basic theming an ownCloud instance.

Contributions from me (jon-tlmi) provided free as in beer and free as in copyright. 

###Configuration

The themes directory within ownCloud is the container for all theming files.
A folder with the name of the theme should be placed within the themes
directory and linked to ownCloud via the config.php file.
The folder structure of a theme has to be exactly the same as the main ownCloud
structure (owncloud/core for example).

It is possible to override js files, images, and templates and css files with
customized versions.
Configuration file

The ownCloud config.php file contains the link to the theme.
When developing a theme, enter the following line into config.php:

```
  "theme" => 'themename';
```

Here, themename is the folder in the themes directory. In this example I've used 'demotheme'

###Customize the logo

In order to customize the logos, create images which meet the specs below and
place them in the themes/core/img directory within the ownCloud instance.

Logo.svg

This is the splash screen logo appearing above the login page of the ownCloud
instance (SVGs can be created with Adobe Illustrator or Inkscape).  The size of
this image is currently 252x120 pixels.  Any larger and the logo will
not fit properly on the page.

Logo-wide.svg

This is the little logo that appears in the top left of the ownCloud navigate
frame. The size of this image is 140x32 pixels. Though the width may be
larger to meet your needs, the height is fixed.

###Changing Colors

The color scheme is stored in the style.css file within the
owncloud/core/css folder.

To change the color of the header bars, copy the core/css/style.css
to themes/<themename>/core/css/style.css and edit.

Below is shows part of the style.css file which contains the colors.
There are several locations within this file that assign colors.
Scroll through the file to find the desired location and modify as required.

```
  #body-login {
          text-align: center;
          background: #1d2d44; /* Old browsers */
          background: url('../img/noise.png'), -moz-linear-gradient(top, #35537a 0%, #1d2d44 100%); /* FF3.6+ */
          background: url('../img/noise.png'), -webkit-gradient(linear, left top, left bottom, color-stop(0%,#35537a), color-stop(100%,#1d2d44)); /* Chrome,Safari4+ */
          background: url('../img/noise.png'), -webkit-linear-gradient(top, #35537a 0%,#1d2d44 100%); /* Chrome10+,Safari5.1+ */
          background: url('../img/noise.png'), -o-linear-gradient(top, #35537a 0%,#1d2d44 100%); /* Opera11.10+ */
          background: url('../img/noise.png'), -ms-linear-gradient(top, #35537a 0%,#1d2d44 100%); /* IE10+ */
          background: url('../img/noise.png'), linear-gradient(top, #35537a 0%,#1d2d44 100%); /* W3C */
          filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#35537a', endColorstr='#1d2d44',GradientType=0 ); /* IE6-9 */
  }
```

This section of code handles the headers for many different browser types.
The default colors in the above example are #33537a (light blue) and #1d2d42 (dark blue). Some older browsers have only one color, however,
most have gradients.

The login page background is a horizontal gradient. The hex #33537a
is the top color of the gradient at the login screen. The #1d2d42
is the bottom color of the gradient at the login screen.

To change the colors, modify these entries with the desired hex color code.

> hex color code: http://cloford.com/resources/colours/500col.htm
