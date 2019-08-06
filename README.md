


![julia_logo](img/julia_logo-small.png)

&nbsp;

[![Build Status](https://travis-ci.org/DigitalDieter/Julia.svg?branch=master)](https://travis-ci.org/DigitalDieter/Julia)

## Installation / Dependencies

Using scripts/install_julia.sh for automatic julia installation

You need to install the following packages as Installation dependencies:



```sh
# Download julia archiv
wget https://julialang-s3.julialang.org/bin/linux/x64/1.1/julia-1.1.1-linux-x86_64.tar.gz
# Extracting julia archiv
tar -xzvf julia-1.1.1-linux-x86_64.tar.gz
# Change to folder julia
cd julia-1.1.1/
# Create symbolic link for execution
sudo ln -s /home/$(whoami)/julia-1.1.1/bin/julia /usr/local/bin
# Execute julia
julia
```

To use Julia inside your jupyter notebook you have to install the following package inside the julia console:

```jl
using Pkg
Pkg.add("IJulia")
```


Show installed packages
```bash
Pkg.installed()
```

#### To create an executable script copy & paste the following command into the commandline:

```bash
dd of=hello.jl<< EOF
#!/usr/local/bin/julia
println("Hello world")
EOF
chmod a+x hello.jl
```

#### For running the script execute the following command:
```bash
julia hello.jl
```

B+
