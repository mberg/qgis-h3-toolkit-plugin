# H3 Quadkey Toolkit Plugin for QGIS
🌐 Brings the Quadkey and H3 and discrete global grid systems to [QGIS](https://qgis.org/). 

🚀 Powered by the open source [H3 library](https://h3geo.org/) and [Mercantile](https://pypi.org/project/mercantile/)

## How to Install
Browse and install via the plugin manager of QGIS (Recommended). Look for "[H3 Toolkit](https://plugins.qgis.org/plugins/h3_toolkit/)".

You can also install via zipfile (If you need for some reason):
  1. Download a zipped release from the [releases](https://github.com/arongergely/qgis-h3-toolkit-plugin/releases)
  2. Proceed to [Install from ZIP](https://docs.qgis.org/3.22/en/docs/user_manual/plugins/plugins.html#the-install-from-zip-tab) in QGIS

### Installing the `h3` dependency
*TL;DR If you are familiar with Python, this is straightforward via `pip` or `conda`. This is the way to go, for now - I am working to improve the install experience for everyone.*


The plugin depends on the `h3` python package, which you would have to install yourself into the Python environment of QGIS.
At startup the plugin detects if `h3` is missing from the python environment and offers basic guidance on how to install.

**NOTE: The plugin is tested with `h3` version `3.7.x` but in principle should work with other `3.x` versions.**

Please see [H3 Installation](https://h3geo.org/docs/installation) on how to install.

### Installing the `mercantile` dependency

Make sure mercantile is installed to qgis. Eg.

/Applications/QGIS.app/Contents/MacOS/bin/python3.9 -m pip install mercantile

## How to use
The plugin registers an `H3` processing provider, tools are available there.
Please have a look at a tool's help text regarding specific usage.

#### Suggesting improvements / reporting issues
You are most welcome to post suggestions/issues on the [Issues page](https://github.com/arongergely/qgis-h3-toolkit-plugin/issues).

## Developer setup
Assuming a Linux development environment:
1. clone this repository
2. Create a symbolic link in the plugin folder within your QGIS profile directory:
   
   To find your profile folder, open QGIS and navigate to *Settings -> User Profiles* and click on *Open Active Profile Folder*. 
   Then the plugin folder should be `<YOUR PROFILE FOLDER>/python/plugins/`

   `cd` into the plugin folder and create a symbolic link to the `h3_toolkit` folder of this repo. 
   ```shell
   ln -s /your/path/to/qgis-h3-toolkit-plugin/h3_toolkit h3_toolkit
   ```

#### How to make a release
Simply zip up the `h3_toolkit` directory. The .zip file is then ready for [install from ZIP](https://docs.qgis.org/3.22/en/docs/user_manual/plugins/plugins.html#the-install-from-zip-tab)

There is also a convenience `make` command to generate the .zip file:
```shell
make zip
```
