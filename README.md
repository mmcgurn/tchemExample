

# Using built in examples

1. Ssh onto CCR


2. Load the required modules

  ```bash
  
  module purge; module load chrest/ccr gtest openblas/release kokkos/release tines/release tchem/release
  
  or
  
  module purge; module load chrest/ccr gtest openblas/debug kokkos/debug tines/debug tchem/debug
  
  
  ```

3. List Examples

  ```bash
	ls $TCHEM_DIR/example
  ```

4. Getting example for an example
  ```bash
	$TCHEM_DIR/example/TChem_IgnitionZeroD.x --help
  ```


# Using custom code

1. Ssh onto CCR

2. Load the required modules

  ```bash
  
  module purge; module load chrest/ccr gtest openblas/release kokkos/release tines/release tchem/release
  
  or
  
  module purge; module load chrest/ccr gtest openblas/debug kokkos/debug tines/debug tchem/debug
  
  
  ```

3. Clone the example repo

   ```bash
   git clone https://github.com/mmcgurn/tchemExample.git
   ```
   
4. Setup env   
   ```bash
   
   ```
   
5. Setup/build exe
   ```bash
   module load cmake 
   
   mkdir tchemExampleBuilt
   cd tchemExampleBuild
   
   cmake -B . -S ../tchemExample -DTChem_DIR=$TCHEM_DIR/lib64/cmake/TChem
-DTines_DIR=/Users/mcgurn/scratch/tchemv2/install/Tines/lib/cmake/Tines
-DKokkos_DIR=/Users/mcgurn/scratch/tchemv2/install/kokkos/lib/cmake/Kokkos
      
   
