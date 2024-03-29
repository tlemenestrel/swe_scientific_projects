# Software Engineering Scientific Projects

## Introduction

This repository contains a collection of **C++** and **Python** softwares for solving _scientific_ and _engineering_ problems, mostly built using _pure_ C++/Python code. 

## Usage 

To use the code, you can simply build a `conda` environment from the **environment** file. After this, you can use the terminal instructions given for each project.

1. First, build the environment using the provided .yml file:

    ```
    $ conda env create -f swe_projects.yml
    ```

2. Then, run the following command to activate the environment:

    ```
    $ conda activate swe_projects
    ```
    
## Table of Contents

- [Genome Processing](#Genome-Processing)
- [Recommendation Algorithm](#Recommendation-Algorithm)
- [Airfoil Computations](#Airfoil-Computations)
- [Truss Linear Equations](#Truss-Linear-Equations)
- [Image Processing](#Image-Processing)

## Genome Processing

<table>
<tr>
<td>
  
**Genome Processing** is a Python software to generate _DNA references_ and compute the alignments of given DNA sequences with the _generated reference_. 
This allows to identify **regions of similarity** that may be a consequence of _evolutionary relationships_ between the sequences. 

The code generates an **output file** that contains the index of the _matches of each sequence with the reference_ and the _percentage of how many matches
each sequence has_ (i.e. if a sequence matche once, twice or does not match the reference) and the _computing time_.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/genome_processing/images/alignments.png" width="700">
</p>

</td>
</tr>
</table>

### Terminal commands and outputs

1. First, cd into the genome_processing folder:

    ```
    $ cd genome_processing
    ```

2. Then, run the following command to process a given sequence:

    ```
    $ python processdata.py references/ref_3.txt reads/reads_3.txt alignments/align_3.txt
    ```
3. You should get the following output:
    ```
    reference_length: 100000
    number reads: 60000
    aligns 0: 0.15
    aligns 1: 0.75
    aligns 2: 0.1
    elapsed time: 23.56
    ```
<details><summary><b>Show datasets and computing time</b></summary></br>

| Dataset | Reference length | Magnitude | Number of reads	| Reads length | Time and magnitude
|---|---|---|---|---|---|
|1 | 1000       |10<sup>3</sup>		| 600    | 50    | 0.003 s (10<sup>-3</sup>)
|2 | 10000      |10<sup>4</sup>		| 6000   | 50    | 0.1   s (10<sup>-1</sup>)
|3 | 100000     |10<sup>5</sup>	    | 60000  | 50    | 23    s (10<sup>2</sup>)

</details>

## Recommendation Algorithm

<table>
<tr>
<td>

**Recommendation algorithm** is a Python software to compute similarities between movies using cosine similarity and recommend new movies to users. It is made of several functions.

The first one is key_function, an auxiliary function to sort the lines that takes a line of a file as an input. It is later used in the 2nd function sort_file, which takes as input the name of the file to sort and sorts it according to the elements in the first "column" of the txt file, which here is the movie id.

The 3rd function computes the average movie ratings and takes as input a dictionnary which it will use to store the values and the input dictionnary with the movies and their ratings.

The 4th function writes the final output file and iterates over the dictionnary and its sub dictionnaries to print out the movie id, its match (with the id) and the cosine similarity score. The file is finally according to the input filename in the .txt format.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/recommendation_algorithm/images/cosine.png" width="700">
</p>

</td>
</tr>
</table>

### Terminal commands and outputs

1. First, cd into the recommendation_algorithm folder:

    ```
    $ cd recommendation_algorithm
    ```

2. Then, run the following command to run the software on the ml-100k dataset:

    ```
    $ $ python similarity.py ml-100k/u.data similarities.txt
    ```
    
3. You should get the following output:
    ```
    Input MovieLens file: ml-100k/u.data
    Output file for similarity data: similarities.txt
    Minimum number of common users: 5
    Read 100000 with total of 1682 movies and 943 users
    Computed similarities in 121.71 seconds
    ```

## Airfoil Computations

<table>
<tr>
<td>

**Airfoil Computations** is a Python software to compute the _coefficient lift_ of an airfoil depending on **alpha**, the _angle of attack_. For that, various data files are given in a directory. The code reads the _directory_, finds the name of the different input files and computes the **lift coefficient** for each angle of attack.

It is able to read any data for a specific angle of attack and compute the lift coefficient for it. Therefore, it does not require the user to give the angles of attack as inputs. Finally, it has several **error checking** and **exception generation** to check that the user had provided the right _path_ to the directory for the data files, that any of the required _data files_ were found in the data directory and if an **error** was detected when reading an input file.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/airfoil_computations/images/angles.png" width="700">
</p>

</td>
</tr>
</table>

### Terminal commands and outputs

1. First, cd into the airfoil_computations folder:

    ```
    $ cd airfoil_computations
    ```

2. Then, run the following command to process the data of one of the example directories:

    ```
    $ python main.py naca0012/
    ```
    
3. You should get the following output:
    ```
    |alpha  | cl      |stagnation pt|
    |-----  |-------  |--------------------------|
    |-3.00  |-0.3622  |( 0.0030,  0.0094)  0.9906|
    | 0.00  | 0.0000  |( 0.0000,  0.0000)  0.9944|
    | 3.00  | 0.3622  |( 0.0030, -0.0094)  0.9906|
    | 6.00  | 0.7235  |( 0.0099, -0.0170)  0.9967|
    | 9.00  | 1.0827  |( 0.0219, -0.0246)  0.9977|
    ```

## Truss Linear Equations

<table>
<tr>
<td>
  
**Truss Linear Equations** is a Python software to define a Truss class for loading and analyzing a 2D truss using the method of joints.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/truss_linear_equations/truss.png" width="700">
</p>

</td>
</tr>
</table>

### Terminal commands and outputs

1. First, cd into the truss_linear_equations folder:

    ```
    $ cd truss_linear_equations
    ```

2. Then, run the following command to process the data of the beams and truss files:

    ```
    $ python main truss1/joints.dat truss1/beams.dat
    ```
    
3. You should get the following output:
   ```
   Beam       Force
   ----------------
      1       0.000
      2      -1.000
      3       0.000
      4      -1.000
      5       0.000
      6       0.000
      7      -0.000
      8      -1.414
   ```
   

## Maze solver

<table>
<tr>
<td>

Maze Solver is a c++ software to solve a maze, given as an input txt file as a 2D array. It uses the right-hand wall following algorithm. Based on the current location and direction, the algorithm changes direction and/or moves to a new location to find the way out.

The code checks if the command line arguments are provided and reads them, reads the input file, first by reading the size of the array and then the maze. Then, it populates the array with 0s everywhere and 1s where there is no wall. After, it finds the entry of the maze by looking at the first row and runs a while loop that while iterate until the exit is found. At each step, the algorithm will attempt to go in different directions and store the positions at each step. Finally, the positions are given in the output file and make up the solution to the maze.

Afterwards, if all the arguments are provided properly, it reads the maze file and stores the dimensions of the maze. Then, it buils a CSR matrix to store the maze (useful because the maze is mostly made of 0s). After, it reads the solution file, checks that the maze was properly entered on the first row, that each position change is valid and that the code reaches the exit of the maze on the last row. Finally, it prints feedback about whether the solution is valid or invalid.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/maze_solver/maze.jpg" width="500">
</p>

</td>
</tr>
</table>

## Image Processing

<table>
<tr>
<td>

Image processing is an important category of computations utilized in many science and engineering fields. Some important computations in image processing include focus detection and various filtering operations to smooth or sharpen an image, detect edges, etc.

The goal of this project is to developp a C++ image class that can read and write JPEG files, and has methods to compute the sharpness of the image and smooth the image using a box blur kernel of a specified size.

<p align="center">
<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/image_processing/boxblur.png" width="700">
</p>

</td>
</tr>
</table>

### Code description

The code first implements an image class with a constructor that accepts a string
containing the name of the JPEG file to be read. The constructor reads the file 
and stores the image data as a data attribute. It calls a function called
ReadGrayscaleJPEG(), which is pre-defined.The class also has a Save() method that writes the current version of the image 
to a JPEG file. It takes a string containing the name of the JPEG file to be 
written. However, if the string is empty the original filename is used instead.

Afterwards, the class has a Convolution() method. It has specific requirements
for both the kernel and the input and output. First, the input and output should
 be of the same size. Second, the method only supports square kernels of odd 
 sizes and at least size 3. Then, it has a BoxBlur() method that takes an argument specifying the kernel 
size and calls the Convolution() methd to smooth the image. Also, it uses a Sharpness() method that returns the sharpness of the image. 

Finally, the main file loads the image stanford.jpg and computes and outputs 
the sharpness for kernel sizes of 3, 7, . . . , 23, 27 and then compute and 
output the sharpness of the resulting images.

<img src="https://github.com/tlemenestrel/swe_scientific_projects/blob/master/image_processing/matrix.png" width="500">
