# placingtask_2010-2011_textual_metadata
MediaEval Placing Task 2010 &amp; 2011 Textual Metadata Datasets

## Introduction


This site contains the textual metadata datasets used by the participants of the Placing Task at MediaEval 2010 and MediaEval 2011. MediaEval is a multimedia benchmark initiative and the Placing Task was one of several tasks in 2010 and 2011. Placing Task participants tried to automatically guess the location of a video, i.e., assign geo-coordinates (latitude and longitude) to videos using one or more of: textual video metadata (tags, titles, social information,...), visual content, and audio content.



Note that this site *only* contains the textual metadata. If you would like the videos and images, you need to download them yourself using the links in the metadata. Note that a set of visual and audio features were available in the benchmark (please contact the organizers to obtain these data).



Placing Task Participants could make use of metadata and audio and visual features as well as external resources. Under no circumstances the participants were allowed to re-find the provided videos on-line and use actual geotags (or other related data) for preparing their runs. Ground truth was supplied by Flickr users that uploaded the videos and the images. All metadata were shared by their owners under Creative Commons license.


## MediaEval 2010 Placing Task dataset


The dataset was composed by 5125 and 5091 videos for the development and test sets respectively and the metadata of a set of 3,185,258 geotagged Flickr images. A set of basic visual features extracted for all images and for the frames of the videos was provided.


### Development and Test datasets


Metadata for videos (which was collected from Flickr) is contained in XML files. In most cases, the XML fields of the metadata were self-descriptive. Besides the Title, Tags, Description, Comments and Location of the videos, it was also included information about the User who uploaded the videos and about his/her Contacts, his/her Favourites and the list of all videos she/he has uploaded in the past. Please, note that tags are contained in the field . The development set comes with the ground truth values for each video. This information is contained in the metadata in the field .


  [MediaEval 2010 Placing Task development set original XML files](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/DevelopmentSet_Metadata_PlacingTask_2010.tar.gz)  
  [MediaEval 2010 Placing Task test set original XML files](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/TestSet_Metadata_PlacingTask_2010.tar.gz)  
  [MediaEval 2010 Placing Task test set groundtruth](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/groundtruth_testset_mediaeval2010.txt)  
  [MediaEval 2010 Placing Task test set groundtruth (coordinates only)](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/groundtruth_testset_mediaeval2010_coordinates.txt)  

### Flickr images metadata dataset


The MediaEval Placing Task organizers provided a Flickr images dataset useful for development purposes. Using geographic bounding boxes of various size and the Flickr API, they collected metadata for 3,185,258 CC-licensed Flickr photos uniformly sampled from all parts of the world. Most, but not all, photos have textual tags. All photos have geotags of at least region level accuracy. Accuracy shows what zoom level the user used when placing the photo on the map. There are 16 zoom and hence 16 accuracy levels (e.g., 6 - region level, 12 - city level, 16 - street level). Note that they include Flickr images since they are potentially helpful for development purposes. The test set, however, included only videos.


[Flickr Images Dataset (about 3.2 million images)](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/photos-meta.zip)

The Flickr images dataset is a text file in with each line represents the information related to a photo.

Example:


75905404@N00/3089149570 : http://farm4.static.flickr.com/3148/3089149570_f7145e094a.jpg : GeoData[longitude=150.69044 latitude=-33.751354 accuracy=15] : flowers flower australia nsw newsouthwales agapanthus pemrith  : 1228560221000 : 1228640133000  

So, each line has the format: UserID/PhotoID : HTMLLinkToPhoto : GeoData[longitude latitude accuracy] : tags : DateTaken : Date Uploaded  
UserIDs and PhotoIDs are Flickr user and photo identifiers, dates are unix timestamps, links are to medium sized photos.


## MediaEval 2011 Placing Task dataset

The data set is an extension of the 2010 Placing Task data set and contains a set of geotagged Flickr videos (~15,000 for development and test purposes) as well as the metadata for geotagged Flickr images (~3.2 million). A set of basic visual features extracted for all images and for the frames of the videos was provided. Evaluation of runs submitted by participating groups was based on distances between the predicted and the actual geo-coordinates.



Development data is the combination of the development and test data from the MediaEval 2010 Placing Task. The two sets are pooled to form the 2011 development set. The test set has been reduced to 5,347 videos in total.



A set of basic visual features extracted for all images and for the frames of the videos was provided. All videos and images were shared by their owners under Creative Commons license.

Note: Please note that the task requires you to predict the latitude and longitude for each video. The development set comes with the ground truth values for each video. This information is contained in the metadata in the field .

  [MediaEval 2011 Placing Task development set original XML files](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/DevelopmentSet_Metadata_PlacingTask_2011.tar.gz)  
  [MediaEval 2011 Placing Task test set original XML files](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/TestSet_Metadata_PlacingTask_2011.tar.gz)  
  [MediaEval 2011 Placing Task test set groundtruth](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/groundtruth_testset_mediaeval2011.txt)  
  [MediaEval 2011 Placing Task test set groundtruth (coordinates only)](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/groundtruth_testset_mediaeval2011_coordinates.txt)  

*[Flickr Images Dataset (~ about 3.2 million images)](https://github.com/dferres/placingtask_2010-2011_textual_metadata/blob/master/photos-meta.zip)


Flickr images (useful for development purposes) For development purposes they provided metadata and low-level visual features extracted from a large set of Flickr images. If you would like the images, you need to download them yourself using the links in the metadata.


## Evaluation


Evaluation of runs submitted by participating groups was based on distances between the predicted and the actual geo-coordinates. Ground truth is supplied by Flickr users uploaded the videos and the images. 


Evaluation was done by calculating the distance from the actual point (assigned by a Flickr user) to the predicted point (assigned by a participant).  The compared runs by finding how many videos were placed at least within some threshold distance  (1 km, 5km, 10km, 50km and 100km.) from the ground truth.


Claudia Hauff provided an Evaluation Script in his website [http://www.st.ewi.tudelft.nl/~hauff/PlacingTask2013/eval](http://www.st.ewi.tudelft.nl/~hauff/PlacingTask2013/eval)


## References & Citation


If you use the Placing Task 2010 and/or 2011 textual metadata datasets, please cite the this paper:


* Martha Larson, Pascal Kelm, Adam Rae, Claudia Hauff, Bart Thomee, Michele Trevisiol, Jaeyoung Choi, Olivier Van Laere, Steven Schockaert, Gareth J. F. Jones, Pavel Serdyukov, Vanessa Murdock, Gerald Friedland.  
 _The Benchmark as a Research Catalyst: Charting the Progress of Geo-prediction for Social Multimedia._
  _Multimodal Location Estimation of Videos and Images (Springer Publishing), 2014._
 [[pdf]](http://link.springer.com/chapter/10.1007%2F978-3-319-09861-6_2) [[bibtex]](http://dblp.uni-trier.de/rec/bib2/books/daglib/p/LarsonKRHTTCLSJSMF15.bib)  



The Placing Task 2010 was organized by: Pavel Serdyukov (Delft University of Technology) and Vanessa Murdock (Yahoo! Research).
The proceedings of the MediaEval 2010 workshop are available online at [http://www.multimediaeval.org/mediaeval2010/2010worknotes/](http://www.multimediaeval.org/mediaeval2010/2010worknotes/).



The Placing Task 2011 was organized by: Vanessa Murdock (Yahoo! Research), Adam Rae (Yahoo! Research), Pavel Serdyukov (Yandex), and Pascal Kelm (Technical University of Berlin). The proceedings of the MediaEval 2011 workshop are available online at [http://ceur-ws.org/Vol-807/](http://ceur-ws.org/Vol-807/)

The Placing Task 2011 overview paper data:

* Adam Rae and Vanessa Murdock and Pavel Serdyukov and Pascal Kelm.  
 _Working Notes for the Placing Task at MediaEval 2011_ [[pdf]](http://ceur-ws.org/Vol-807/Rae_Placing_me11overview.pdf) [[bibtex]](http://dblp2.uni-trier.de/rec/bib2/conf/mediaeval/RaeMSK11.bib)  


## Legal Disclaimer
The author of this site assumes no responsibility for the correctness and use of the information and data contained in this site.

