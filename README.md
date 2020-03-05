This program is for finding the base-pair network In RNAs.
 It assumes a .out or .rob file as its input.
 In case of .rob file it expects .out file as well.
 In both the cases, it assumes the .dat file.
 The switches are:
     -netsize=5 (prints only network of size 5), Default is 3
     -netsize=5-10 (prints only network of size 5 to 10), Default is 3-30
     -exdeg=3  (Prints ann networks with at least a vertex with degree 3
                (Default is 2)
     -cycles=2 (Computes the number of cycles, Main cycles), Default 0     -outformat=new/old (default new)
     -ovlpcutoff=20.0 for non-base pair overlap cutoff value
     -adj=true for creation of adjacency matrix. Default false


 It generates a .edge file for edge lists, .adj(optional) file for adjacency
 matrix for every file. It also generates a pairchain.net for all files.
 It works for multiple files, like, bpnet *.out -netsize=4 -exdeg=3
 
 
 Compilation:   g++ -std=c++03 -static -I./include main.cpp -o bpnet
 
 run:    ./bpnet [optional switches] 1a9n.out 
 
 file format: The format of the edge file
 
GRAPHMDL   180  # unique model number for the network

META DEGREE  2 COUNT  3  # three vertex with degree 2

META CYCLE     1   # cycle found

META CARD     3    # cardinality or vertex size is 3
        


DATA   180   225     A:A-W:SC     1.27 T:T BP   191   0   236   0   A   A

DATA   180   423     A:U-H:WT     0.48 T:T BP   191   0   434   0   A   U

DATA   225   423     A:U-w:sT     0.40 T:T BP   236   0   434   0   A   U

TER

The columns are 

Tag    corid corid    bptype      eval dat:dat type cifid chn cif  chn  res res 

type is BP for base-pair OL for overlap.




