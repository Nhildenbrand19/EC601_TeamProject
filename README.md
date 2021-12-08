## Problem Statement
The project being discussed in this report is one that was found on Kaggle, a platform designed to propose machine learning projects and provide rewards for submitting functioning solutions. This project centers its focus on a partnership with the National Football League (NFL), as a continuation of an earlier project. Previously, the Kaggle community was provided with a dataset from sensors on football players which allowed the development of a detection algorithm for when a players’ helmet was impacted. Now, the NFL would like the ability to automatically track helmets and the players to whom they belong to on video. In combination with the previous helmet impact detection algorithm, the NFL hopes to use these tools in order to help answer questions related to player safety and the effects of helmet impacts on players over time.

The topic of player safety and both the short and long term effects of severe impacts on players has been a central focus in the NFL and broader impact sports community for several years. As research on Traumatic Brain Injuries (TBIs) and Chronic Traumatic Encephalopathy (CTE) continues to surface and gain traction, many participants in impact sports- such as football- have begun asking questions. The most damning hypothesis is that players involved in football- especially those having played for many years- are at a high risk of having experienced more than one TBI over the course of their long sporting careers. The repeated exposure of the human brain to traumatic injuries appears to significantly increase the likelihood that an individual will develop CTE, Alzheimer’s, dementia, and other neurodegenerative diseases. In an effort to minimize players’ exposure to TBIs, education campaigns have sought to educate players and coaches on the dangers of impacts to the head. Additionally, rule changes and new pad and helmet designs over the years have helped provide better protection for the players. However, even with the significant progress that has been made so far, many competitive players still experience TBIs in the form of concussions, and are therefore still at a higher risk of suffering from various neurodegenerative diseases later in life. A new study that was published in the Journal of the American Medical Association examined the brains, donated to Boston University, of 202 deceased football players. These players played at a variety of levels from High School all the way up to the NFL. The brains were analyzed for CTE, in conjunction with player history on the field. Of the 202 players, 87% were diagnosed with CTE, while 111 of these players played in the NFL, 110 of which were diagnosed with CTE. This is a very scary, yet very real issue in not only the NFL, but major contact sports around the world and this product aims to help.

### Links to these articles
- [Time Article](https://time.com/4871597/degenerative-brain-disease-cte-football/)

- [CTE](https://www.mayoclinic.org/diseases-conditions/chronic-traumatic-encephalopathy/symptoms-causes/syc-20370921)

-------------

## Technologies and Literature Review
In an effort to help researchers and protect their players, the NFL has provided large datasets including video files from hundreds of games as well as sensor data from players’ helmets. The first step, as previously mentioned, was to interpret the helmet sensor data in order to understand what an impact looked like. Now, the task at hand is to tie the data from the helmet sensors to video of the plays in real time. In order to do this, several approaches have been employed. The first order of business is to gain the ability to track helmets and players directly from the provided video files. Fortunately, many of the participants in the Kaggle challenge have shared their work in the open source spirit. The most promising approach appears to be utilizing a modified version of the Deep SORT algorithm. This algorithm was developed to track objects in video, so it is highly useful in this project. In this case, the approach focuses on modifying the algorithm to track each individual players’ helmet rather than the whole player. This approach splits apart all of the video frames, attempts to find all of the helmets in each of the frames, and then clusters together all of the frames where it thinks it can track the same helmets over a period of time, therefore producing a prediction of sorts for which helmet is where and where it moves over time. Of course, the biggest issue with this approach, as with nearly all deep SORT algorithms, is occlusion. Since players tend to group together and in tight formations, overlapping and disappearing helmets for single or sometimes several video frames is bound to happen. The method of separating the video frames and then clustering those that have the same labeling for the same helmets over time is an attempt to circumvent this issue, so that the frames where helmets cannot be detected or overlap can be more safely ignored. A vast majority of the code holding an Apache 2.0 open source license which means that we are able to reproduce and distribute copies of the work or derivatives of the work in any form. The majority of all open source documentation uses an adaptation of DeepSort along with helmet mapping, to determine an exposure, along with the tracking of helmets and their associated players.

The second part of the leading approach is to read the number from the players’ jersey in order to determine which helmet sensor data set they represent. This is being done currently only by one contributor utilizing the language detection code available through the EasyOCR open source github page. While this approach appears to work fairly well for a first attempt, there are other potential solutions that have been developed that may better suit this situation. Notably, a publication from the University of Waterloo details a method for the detection of player numbers on jerseys in the game of hockey. While this code is not publicly available, it is sometimes possible to contact the authors of the publication and be granted access to the codebase. Assuming this is a possibility, this computer vision software may work significantly better with almost no tweaking whatsoever, namely due to the fact that it is already developed for use on sports jerseys. Additionally, the fast movement in hockey causing motion blur is not dissimilar to the movements found in football, so this detection and labeling algorithm would likely yield more accurate results overall. The above combined approaches appear to be the most popular and the ones with the most promise. While there are others, they are not notably better in any way than the leading ones, and since the leading ones have garnered the most attention, they have received the most updates. In fact, recently, the Deep SORT implementation for helmet tracking received an update that enabled 5X faster performance than previously possible.

### Links to Open Source
- [Tuning DeepSort](https://www.kaggle.com/firefliesqn/tuning-deepsort-helmet-mapping)
- [Helmet Mapping](https://www.kaggle.com/its7171/nfl-baseline-simple-helmet-mapping)
- [Starting Guide](https://www.kaggle.com/robikscube/nfl-helmet-assignment-getting-started-guide)

----------

## Users and Applications
The users of this project is first and foremost the NFL. The NFL wants this information to help mitigate the risk associated with playing in their league and to ease the minds of those concerned with the safety. Secondly, we believe that the NFLPA, or the NFL Players Association, should have access to this information to better self-assess not only their style of play, but their health and duration of career. We truly believe that if players were equipped with this type of information, we would see the way players approach the game differently, along with dramatically shorter careers across all positions. This though may not be something that the NFL wants shared with the players. Thirdly, we believe that medical professionals would be another group of users. This type of information can drastically help in the diagnosis and link to CTE that some players develop. Additionally, employees at AWS will be users as this is something that they will be supporting and monitoring. Lastly, parents and players not in the NFL may use this product as well, assuming they are given access. This will give the ability to make much more informed decisions about their futures in football and whether they allow their children to continue. While these are just a handful of users specific to this football project, we do believe that this product can be applied to many other contact sports.

------------

## MVP (Minimum Value Product)
The minimum value product in this case is quite a bit. We first need the video footage of the game. We need that video footage to be from the endzone view and the sideline view to be able to properly analyze the game. This footage will be provided by the NFL and AWS in this case. It is vital to this project to have the two locations specified for the camera angle. Next, we need to be able to analyze the distinction between what is a helmet and not a helmet. We are focused specifically on head traumas and it is vitally important to make sure that other parts of the body or equipment are not counted as the helmet. Some players may take many more body blows than head shots, and that is not something that we can afford to double count. This comes in the form of helmet mapping and for our situation, this is part of the MVP. We also need to be able to recognize player number to link the helmet and player together. This is very important to distinguish which players take the most hits to the head and properly diagnose the issue. We can again run into the issue of double counting if the numbers of the players are incorrectly predicted. Lastly, we need to confirm what an exposure  is and collect that information for each player. An exposure can mean many different things to different people and that determination needs to be confirmed to attain accurate information. There needs to be a standard for counting an exposure and apply it to our video.

-----------------------

## Setup of Development Enviroment

When we first looked at running the code and attempting to simulate results, we first needed to make sure all necessary libraries were installed. This was necessary to be able to import the needed libraries in the code. Once this was done, we then needed to make sure that we had the correct files downloaded for the code to read, while also making sure that the filepath to these files was correctly indicated in each block of code. Parts of the code were correctly simulated, while others have been running for 20+ hours. For this example, we were given the two following videos, one with a angle from the endzone, and the other with an angle from the sideline. Both starting videos are shown below.


https://user-images.githubusercontent.com/74614080/133801835-4213a1dd-f89b-4d28-9a22-8f88bd6f6880.mp4



https://user-images.githubusercontent.com/74614080/133801859-285549a9-6321-4768-bdd5-41d4de569a7a.mp4

-------

### References
- [NFL Assignment](https://www.kaggle.com/c/nfl-health-and-safety-helmet-assignment/code)
- [Yolo v5 Guide](https://www.kaggle.com/duythanhng/nfl-yolov5-deepsort-pytorch-guide/notebook)
- [Helper Submission](https://www.kaggle.com/robikscube/helper-code-helmet-mapping-deepsort/notebook)
- [DeepSort Code Reference](https://www.kaggle.com/s903124/nfl-helmet-with-yolov5-deepsort-starter)
- [DeepSort Article](https://nanonets.com/blog/object-tracking-deepsort/)
- [Sort Article](https://arxiv.org/pdf/1703.07402.pdf)
