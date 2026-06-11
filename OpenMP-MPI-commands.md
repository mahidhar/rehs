Copy the files for the hands on:

```
cp -r /expanse/projects/qstore/use300/rehs $HOME/
cd $HOME/rehs
```

### Command Set #1 ###
<br>
OpenMP Example
<br>

Lets start by loading a compiler:

```
module reset
module load gcc/10.2.0
```
Compile the OpenMP code and run:
```
gcc -fopenmp -o pi_openmp pi_openmp.c
sbatch -A abc123 --cpus-per-task=8 pi_openmp.sb
```
Once this job runs, check the output file!
### Command Set #2 ###
<br>
MPI Point to Point Examples
<br>

Lets start by loading the compiler modules. We are using GNU compilers and MVAPICH2 MPI compiler.

```
module reset
module load gcc/10.2.0
module load mvapich2/2.3.7
```
Compile and run the MPI code:
```
mpicc -o blocking.exe blocking.c
sbatch -A abc123 blocking.sb
```
Once this job runs, check the output file!

### Command Set #3 ###
<br> 
MPI Collectives Examples
<br>

Lets pick a different compiler combination:


```
module reset
module load intel/19.1.3.304
module load openmpi/4.1.3
```
Compile and run MPI Broadcast and MPI Reduction examples.

```
mpif90 -o bcast.exe bcast.f90
sbatch -A abc123 bcast.sb

mpif90 -o factorial.exe factorial.f90
sbatch -A abc123 factorial.sb
```
### Command Set #4 ###
<br> 
MPI Calculating Pi example
<br>

First we set up our MPI compiler environment:
```
module reset
module load gcc/10.2.0
module load mvapich2/2.3.7
```

Compile and run the example

```
mpicc -o pi_mpi.exe pi_mpi.c
sbatch -A abc123 pi_mpi.sb
```

