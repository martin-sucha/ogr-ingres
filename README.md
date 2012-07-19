OGR Ingres Driver
=================

This version uses GDAL 1.9.1 source. If you need a plugin for
another version (e.g. 1.8), it should suffice to download the GDAL source
and replace the `ogr/ogrsf_frmts/ingres` directory with the one
from this repository.

Configure with Ingres:

```bash
. ~ingres/.ingIIsh
./configure --with-ingres="$II_SYSTEM"
```

Build OGR Ingres plugin (as a shared object):

```bash
cd ogr/ogrsf_frmts/ingres
make plugin
```

Then, copy the plugin to GDAL plugin directory (which may not
exist on your system - just create it):

```bash
sudo mkdir -p /usr/lib/gdalplugins/1.9
sudo cp ogr_Ingres.so /usr/lib/gdalplugins/1.9
```
