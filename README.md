# ipole
polarized covariant radiative transport code

# building

You can build the ```ipole``` executable by using the python build script as follows
```bash
$ python build.py [MODEL]
```
where ```[MODEL]``` specifies the fluid data format. For all fluid data produced from illinois codes after September 2018, the ```iharm``` model should be used.

# running

ipole can be run using either parameter files or command line arguments. 

### parameter files

### command line arguments

If no parameter file is specified, then ipole reads arguments in the following format

```bash
./ipole thetacam freqcgs Mbh M_unit path/to/dump counterjet

# as example
./ipole 17 230.e9 1.e8 2.3e21 /data/bh28-fs1/dumps/iharm/mad/0.9375_256x128x128/dumps/dump_00000000.h5 0
```

```thetacam``` should be given in degrees away from the polar axis.

```freqcgs``` is the desired frequency for the image (given in Hz).

```Mbh``` is the mass of the central black hole in units of Msun (overwritten if the dump comes from a GRRMHD run)

```M_unit``` is the mass unit for the simulation in cgs (overwritten if the dump compes from a GRRMHD run)

```path/to/dump``` is the absolute or relative path to the fluid dump file

```counterjet``` is one of {0,1,2} and specifies if certain parts of the domain should be "switched off" for emission. If counterjet == 1, only emission from X[2] > 0.5 is allowed. If counterjet == 2, only emission from X[2] < 0.5 is allowed. Otherwise, emission from all parts of the domain is allowed.


