## Image-Matching
The goal of this assignment is to use list and hashtable for the image search task.

The objective of this project is to use and evaluate lists and hashtable for the task of image matching. Image matching is a common problem where the task is to search over a collection of images to find an image similar to the query image. This task typically requires the following steps:

#### Query Image
For each image in the collection of images, compute an image representation that can be stored in a data structure
For the query image, compute the image representation and search the stored representations to find a match
The focus of this assignment is on the use of data structure for storing the representation and any additional information to facilitate the search and matching. You will explore the use of list and hashtable and compare the two in facilitating search. You are provided implemented class for the hashtable data structure in the file dpcourse/HashTable.py. 
In addition, you are also provided a skeleton implementation of the image search class in the file imageops/ImageSearch.py. Several methods of the class are also already implemented. Since the focus of this assignment is on data structure for store and search, methods necessary for generating the image representation are already implemented. The primary method to be used is __difference_hash(), which takes as argument the input image and its width and height and returns as a list a representation key and a 64 dimensional binary array.

#### Implementing 4 Key Methods:
  * create_search_index() - create a list data structure to store the image representation, associated binary array, and the image file name
  * create_search_index_hash() - create a hashtable data structure to store the image representation, associated binary array, and the image file name
  * find_match_in_list() - search the list data structure match the query image
  * find_match_in_hash() - search the hashtable data structure match the query image

#### The logical steps necessary in the 2 methods for creating the data structure are:
  * Initialize the data structure
  * Read image files from the search directory specified by the main program
  **For each image:**
  * convert to gray scale if the image is color
  * compute the image representation (__difference_hash())
  * store the representation along with name of the read image

#### The logical steps necessary in the 2 methods for searching the data structure to match the query image are:
  * Read query image
  * Convert to gray scale if the image is color
  * Compute the image representation (__difference_hash())
  * Search the data structure to find match based on the image representation
  **If the match includes more than one image:**
  * compute hamming distance between the binary array of the query image and that of each matched image (__hamming())
  * select the best match as the one that has the lowest hamming distance
  * Return the matched image
