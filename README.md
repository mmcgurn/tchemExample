

# Using built in examples

1. Ssh onto CCR

1. Load the project modules ```module use /projects/academic/chrest/modules/```

2. Load the required modules

  ```bash
  
  module purge; module load chrest/release 
  
  or
  
  module purge; module load chrest/debug 
  
  
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

1. Load the project modules ```module use /projects/academic/chrest/modules/```

2. Load the required modules

  ```bash
  
  module purge; module load chrest/release 
  
  or
  
  module purge; module load chrest/debug   
  
  ```

3. Clone the example repo

   ```bash
   git clone https://github.com/mmcgurn/tchemExample.git
   ```

5. Setup/build exe
   ```bash
   
   mkdir tchemExampleBuild
   cd tchemExampleBuild
   
   cmake -B . -S ../tchemExample -DTChem_DIR=$TCHEM_DIR/lib64/cmake/TChem -DTines_DIR=$TINES_DIR/lib64/cmake/Tines -DKokkos_DIR=$KOKKOS_DIR/lib64/cmake/Kokkos
   
   make -j 8
   ``` 
     
6. Running the example
   ```bash
   # Using grimech
   ./exe --inputs-path=$TCHEM_DIR/example/data/ignition-zero-d/gri3.0/ --use-prefix-path=true
   
   # using custom yaml
   ./exe --useYaml=true --chemfile=../tchemExample/inputs/LL2KGB_AllRange.yaml --samplefile=../tchemExample/inputs/sample.dat
   ```
