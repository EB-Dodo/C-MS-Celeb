# C-MS-Celeb
This is a clean version of MS-Celeb-1M face dataset, containing 6,464,018 images of 94,682 celebrities.
Since the original [MS-Celeb-1M](https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/) has too much mislabeled images, we would like to clean this dataset for better model training.

The paper of our cleaning work, "A Community Detection Approach to Cleaning Extremely Large Face Database", can be found [here](https://www.hindawi.com/journals/cin/2018/4512473/abs/)

## Data overview
Our C-MS-Celeb cleaned dataset has 6,464,018 images belonging to 94,682 celebrities.
The table below compares ours with other publicly available cleaned MS-Celeb datasets:

| Datasets | Celebrities |  Images  |
| :--------: | :--------:| :------: |
| Original Dataset |  99,892  |  8,456,240 |
| XiangWu's Cleaned Dataset |  79,099  |  5,049,824 |
| MS-Celeb-1M WashList Cleaned Dataset |  78,579 |  4,621,640  |
| C-MS-Celeb Cleaned Dataset |  **94,682** |  **6,464,018**  |

Our C-MS-Celeb is **large, clean and diverse**.

### Large
First, from this table, compared with other cleaning lists, we can see that C-MS-Celeb preserves more people with more images during the cleaning. 

### Clean
Second, based on our empirical evaluation, approximate 97.3% of images in C-MS-Celeb are correctly labeled.

### Diverse
Third, our community detection based cleaning method can also preserve the diversity of facial images for each individual.
Here are some sample images from "Lady Gaga" and "Quinn Cummings" in our cleaning result:

<img src="https://github.com/JinRC/C-MS-Celeb/blob/master/sample_images.png" width="600">

From these sample results, we can see that images with diverse makeups can be preserved during cleaning (Lady Gaga on the left half).
The diversity of different ages can also be observed from the cleaning results (Quinn Cummings on the right half).

## Our cleaning method based on community detection
We develop a community detection based pipeline to clean the noisy MS-Celeb-1M face dataset. 
As the diversity of faces is preserved in multiple large communities, our cleaning results have both high cleanness and rich data diversity. More details can be found in our paper [here](https://www.hindawi.com/journals/cin/2018/4512473/abs/).

The picture below shows the images of Phil Upchurch before and after our cleaning

<img src="https://github.com/JinRC/C-MS-Celeb/blob/master/before_after.png" width="600">

Images with red squares on the left are mislabeled images in the MS-Celeb-1M face dataset and images on the right are our cleaning results. We can again see that diverse Phil Upchurch of all ages is preserved during the cleaning.

The diagram below illustrates our community detection based cleaning method. We first construct a face similarity graph using pre-trained face recognition models. Each node in the similarity graph represents one image and the weight of the link between two nodes quantifies the similarity between these two images. Then we remove the weak links and run the community detection algorithm on this graph. Finally, we preserve the images in the large communities (colored communities on the right in this diagram) and remove the scattered nodes and minor communities (grey nodes in the diagram). Thus, we are able to achieve both high cleanness and rich data diversity during the data cleaning.

<img src="https://github.com/JinRC/C-MS-Celeb/blob/master/community_detection_clean.png" width="600">


## Benefits of using C-MS-Celeb to train a face recognition model
We use our C-MS-Celeb dataset to train a face recognition model and the image below shows that using C-MS-Celeb for model training can increases the model's performance. Check [our paper](https://www.hindawi.com/journals/cin/2018/4512473/abs/) for more benefit details.

<img src="https://github.com/JinRC/C-MS-Celeb/blob/master/PR-curve.png" width="400">

## How to use C-MS-Celeb
C-MS-Celeb has two TXT files in clean_list.7z: "clean_list_128Vec_WT051_P010.txt" and "relabel_list_128Vec_T058.txt", which are the cleaned lists of facial images.

"clean_list_128Vec_WT051_P010.txt" contains the path of all cleaning results in Stage 2 (See our paper for more details). 
"relabel_list_128Vec_T058.txt" contains the path of all relabeling results in Stage 3 (See our paper for more details). 
For both files, the first column is the identity label of the image and the second column is the path of the image file.


Note that C-MS-Celeb here is only the cleaned label list. In order to use this dataset, one needs firstly download all images of the MS-Celeb-1M dataset and then filter out the noisy (mislabeled) images according to the path in C-MS-Celeb's TXT files. You may need to combine these two TXT files as one before filtering out mislabeled images.
The raw MS-Celeb-1M dataset can be downloaded on this website:
https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/

## Citation information
If you use this face database to train your model, please cite our paper as below:

Chi Jin, Ruochun Jin, Kai Chen, and Yong Dou, “A Community Detection Approach to Cleaning Extremely Large Face Database,” Computational Intelligence and Neuroscience, vol. 2018, Article ID 4512473, 10 pages, 2018. doi:10.1155/2018/4512473

The link of our paper "A Community Detection Approach to Cleaning Extremely Large Face Database" is:
https://www.hindawi.com/journals/cin/2018/4512473/
