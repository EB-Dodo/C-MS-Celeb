# C-MS-Celeb
This is a clean version of  MS-Celeb-1M face dataset, containing 6,464,018 images of 94,682 celebrities.
Since the original [MS-Celeb-1M](https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/) has too much mislabeled images, we would like to clean this dataset for better model training.

The paper of our cleaning work can be found [here](https://www.hindawi.com/journals/cin/2018/4512473/abs/)

## Data overview
Based on our empirical evaluation, approximate 97.3% of images in C-MS-Celeb are correctly labeled.

This face database is the cleaning result in our paper: "A Community Detection Approach to Cleaning Extremely Large Face Database".

## Our cleaning method based on community detection

## Benifits of using C-MS-Celeb to train a face recognitioni model

## How to use C-MS-Celeb
C-MS-Celeb has two TXT files in clean_list.7z: "clean_list_128Vec_WT051_P010.txt" and "relabel_list_128Vec_T058.txt", which are the cleaned lists of facial images.

"clean_list_128Vec_WT051_P010.txt" contains the path of all cleaning results in Stage 2 (See our paper for more details). 
"relabel_list_128Vec_T058.txt" contains the path of all relabeling results in Stage 3 (See our paper for more details). 
For both files, the first column is the identity label of the image and the second column is the path of the image file.


Note that C-MS-Celeb here is only the cleaned lable list. In order to use this dataset, one needs firstly download all images of the MS-Celeb-1M dataset and then filter out the noisy (mislabeled) images according to the path in C-MS-Celeb's TXT files. You may need to combine these two TXT files as one before filtering out mislabeled images.
The raw MS-Celeb-1M dataset can be downloaded on this website:
https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/

## Citation information
If you use this face database to train your model, please cite our paper as below:

Chi Jin, Ruochun Jin, Kai Chen, and Yong Dou, “A Community Detection Approach to Cleaning Extremely Large Face Database,” Computational Intelligence and Neuroscience, vol. 2018, Article ID 4512473, 10 pages, 2018. doi:10.1155/2018/4512473

The link of our paper "A Community Detection Approach to Cleaning Extremely Large Face Database" is:
https://www.hindawi.com/journals/cin/2018/4512473/
