
Getting Started with Chisel
=======================
The following procedure is a walk-through for setting up the environment and running a test program in Chisel. The source code and build file are copied from [Chisel Template Repository](https://github.com/freechipsproject/chisel-template/tree/release)

### Dependencies
The installation commands are tested in Ubuntu 18.04.

#### JDK 8 or newer
```shell
sudo apt install openjdk-8-jre-headless 
```

#### SBT
```shell
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
sudo apt-get update
sudo apt-get install sbt
```

#### FIRRTL and Treadle
```shell
git clone https://github.com/chipsalliance/firrtl.git
git clone https://github.com/chipsalliance/treadle.git
pushd firrtl; sbt publishLocal; popd
pushd treadle; sbt publishLocal; popd
```

#### Chisel Library
```shell
git clone https://github.com/chipsalliance/chisel3.git
cd chisel3
sbt compile
```
### Running the program
```shell
git clone https://github.com/aminiok1/chisel-hello-world.git
sbt test
```

Alternatively, you can generate the Verilog code for the GCD module:
```shell
sbt 'runMain gcd.GcdDriver'
```
