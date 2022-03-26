# Scripts

These scripts retrieve data from Natural Earth's website and computes a the ``data/countries.geojson`` file.

## Install the dependencies

The preparation process work under Linux and Windows (under a git bash session).

The scripts makes use of the wonderful ogr2ogr tool (part of the gdal suite) and a few other shell commands that are glued together with [tuttle](http://github.com/lexman/tuttle), a *make for data*.
Therefore, you'll need to install [git](https://git-scm.com/downloads), [gdal](http://trac.osgeo.org/gdal/wiki/DownloadingGdalBinaries) and [tuttle](https://github.com/lexman/tuttle/releases).

## Run the scripts

Make sure the ogr2ogr tool is available on command line.

After you have checked out the code, go into the script directory and run the processing:

```bash
cd scripts
tuttle run
```

## Docker

There is a tuttle docker container so there is no need to install the above tools. 
Navigate to the root of this project, then run the following:

```bash
docker build -t tuttle ./scripts;
docker run --rm \
--name tuttle \
-v $PWD/scripts/:/tuttle/scripts \
-v $PWD/data:/tuttle/data \
-w /tuttle/scripts \
tuttle \
tuttle run
```
