# Run spin permutations

### Set working directory
setwd("C:/Users/Angelika/Dropbox/PhD/EXPERIMENTS/04_StructureFunction/SCRIPTS") 

###  Load necessary functions
library(matrixStats)
source("rotate.parcellation.R")
source("perm.sphere.p.R")

### Load coordinates as arrays
###### left coordinates
coord_l = scan("coord_lh_Glasser.txt")
coord_l = matrix(coord_l, ncol = 3, byrow = TRUE)
###### right coordinates
coord_r = scan("coord_rh_Glasser.txt")
coord_r = matrix(coord_r, ncol = 3, byrow = TRUE)

### Run 1000 spin permutations
rotate.parcellation(coord.l = coord_l,coord.r = coord_r,nrot = 1000)

### Export to txt
write.table(perm_matrix, file="permutations_Glasser.txt", row.names=FALSE, col.names=FALSE)