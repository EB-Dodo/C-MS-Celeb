# -C-MS-Celeb
A clean version of  MS-Celeb-1M face dataset, containing 6,464,018 images of 94,682 celebrities.

This face database is the cleaning result in our paper: the C-MS-Celeb dataset.

The file list of the C-MS-Celeb are the two TXT files in clean_list.7z: "clean_list_128Vec_WT051_P010.txt" and "relabel_list_128Vec_T058.txt". 

"clean_list_128Vec_WT051_P010.txt" contains the path of all cleaning results in Stage 2. 
"relabel_list_128Vec_T058.txt" contains the path of all relabeling results in Stage 3. 
For both files, the first column is the identity label of the image and the second column is the path of the image file.

In order to use this largest clean dataset, one needs firstly download the MS-Celeb-1M dataset and then copy the images according to the path in both TXT files.

The raw MS-Celeb-1M dataset can be downloaded on this website:
https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/

If you use this face database, please cite our paper below:

