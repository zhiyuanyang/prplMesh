# MultiAP Tools
This project contains maptools.py, a utility for building and deploying multiap SW components.
The directory hirerchy expected by maptools.py is as follows:

```
multiap
└───.repo
└───framework
└───common
└───controller
└───agent
└───tools
│   │   maptools.py
```

Building and installing create build and install directories:
```
multiap
└───.repo
└───build
|   └───install
└───tools
│   │   maptools.py
```


## Prerequisites
<a name="prereq"></a>
Install dependencies listed in [requirements.txt](requirements.txt):

```
pip install -r requirements.txt
```

None sudo users cam add `--user` to the command 

## maptools build & install
By default, maptools build command uses ../build folder for building and installing.
Therefore in order to run multiap binaries/libs, need to add ```LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<...>/build/install/lib``` to the command.

get a list of all supported subcommands:
```
./maptools.py --help
```
subcommand help:
```
./maptools.py <subcommand> --help
```
### Examples
build all (default):
```
./maptools.py build all
```

Build all with nng messaging library (needs to have nng installed):
```
./maptools.py build all -f MSGLIB=nng
```

Clean and rebuild controller only:
```
./maptools.py build controller -c clean make
```

Distclean (removes ../build folder):
```
./maptools.py build all -c distclean
```

## Versioning
<a name="ver"></a>
1.4.0

## Authors
<a name="authors"></a>
* **Tomer Eliyahu**  tomer.b.eliyahu@intel.com

## License
<a name="license"></a>
This project is licensed under the BSD+Pantet License - see the [LICENSE](LICENSE) file for details
