## Ethereum (ETH) wallet docking (I) Ethereum geth client installation
## Ethereum geth client installation
Geth is the official client of Ethereum. It is a command-line tool that provides many commands and options. It can run Ethereum nodes, create and manage accounts, send transactions, mine, deploy smart contracts, etc.
Here are three methods of installing geth:
-Download executable directly
-Online installation
-Compile and install from source code

###  
### Method to download the executable
The simplest way is to download the executable files directly. Ethereum development team provides compiled geth executable files for each system. You can go to the official download address or domestic image to download the compressed package suitable for your system version, decompress it and run it directly. Enter geth help on the command line to see the usage of geth.
-Note 1: geth is a command line tool. You need to run geth on the command line. Windows users do not directly double-click geth.exe.
-Note 2: if you run geth directly without adding any parameters, it will automatically connect to the Ethereum public network and start synchronizing blocks. In Linux system, block data is stored in ~ /. Ethereum by default.
###  
### Method 2 online installation
Ubuntu users can choose to install online and execute the following commands in the terminal:
```
1 $ sudo add-apt-repository -y ppa:ethereum/ethereum
2 $ sudo apt-get update
3 $ sudo apt-get install ethereum
```
After installation, execute geth help to view the usage of geth.
###  
###Method 3 compile and install from the source code
Linux system is recommended for compilation and installation. This paper takes the 64 bit Ubuntu 16.04 system as an example.
Geth is written in go language. Compiling geth source code requires go language and C language compiler. Therefore, go language needs to be installed first. Go1.7 or above is recommended for go language version.
Using make compilation, first download the geth source code go Ethereum. Here, take go ethereum-1.5.6.tar.gz as an example:
Next, unzip the source code:
```
1 $ tar -xzf go-ethereum-1.5.6.tar.gz
```
**1、 Compile with make tool:**
```
$ cd go-ethereum-1.5.6
$ make geth
```
Make will execute the compilation script under the build directory, and the compilation script will call the go language compiler for compilation. Wait more than ten seconds and the compilation is completed. At this time, the geth executable will be generated in go-ethereum-1.5.6/build/bin.
Enter the geth help command, and all commands and options of geth will be displayed:
```
$ cd build/bin
$ ./geth help
```
**2、 Compile with go language compiler**
If you are familiar with go language, you can directly use the go language compiler.
First, download the source code of the go Ethereum project:
```
$ go get -d github.com/ethereum/go-ethereum
```
The above command will download the go Ethereum source code to gopath / SRC / github.com/ethereum/go-ethereum, and download the relevant dependent packages. In the domestic network environment, if FQ is not used, the download will usually fail. At this time, you can refer to the following manual download method.
After downloading, compile with the following command:
```
$ go install -v github.com/ethereum/go-ethereum/cmd/geth
```
Wait for more than ten seconds. After the compilation is completed, the get executable file will be generated in the gopath / bin directory.
-Note: if the go get command is slow or fails to download, you can download it manually: first download go-ethereum-1.5.6.tar.gz, then unzip it to gopath / SRC / github.com/ethereum/go-ethereum, and then go to http://www.golangtc.com/download/package Download golang.org.x.net.tar.gz and unzip it into gopath / SRC. The directory structure after decompression should be as follows:

```
GOPATH/src
├── github.com
│ └── ethereum
│ └── go-ethereum
└── golang.org
└── x
└── net
```

Then compile and install through the go install command above.



To communicate more,contact my telegram:**@jammycode**

