


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

```bash
julia> versioninfo()
Julia Version 1.1.1
Commit 55e36cc308 (2019-05-16 04:10 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
  CPU: Intel(R) Xeon(R) CPU E5-2630 v4 @ 2.20GHz
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.1 (ORCJIT, broadwell)
```

Comments in Julia
```bash
# This is a singleline comment
#=
This is a multiline comment =#
```

```bash
using IJulia
notebook()
```

Vector operations

```bash
# Create a row vector
julia> A = [10, 20, 30]
3-element Array{Int64,1}:
 10
 20
 30
```
Access first element
```bash
julia> A[1]
10
```
Create a column vector
```bash
julia> A = [10; 20; 30]
3-element Array{Int64,1}:
 10
 20
 30
```
Change a value at index 1
```bash
julia> A[1] = 199
199
```
Matrix operations
```bash
julia> M =[1 2 3;4 5 6;7 8 9]
3×3 Array{Int64,2}:
 1  2  3
 4  5  6
 7  8  9
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


## Testing TensorFlow
test tensorflow script
```bash
julia tensorflow_test.jl
```



Pkg.add("MLDataUtils")
Pkg.add("StatsBase")

using MLDatasets

train_x, train_y = MNIST.traindata()
test_x,  test_y  = MNIST.testdata()

using Learn
using MLDataUtils
using StatsBase
using StatPlots

# Set up GR for plotting. x11 is uglier, but much faster
ENV["GKS_WSTYPE"] = "x11"
gr(leg=false, linealpha=0.5)
