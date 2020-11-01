# CZ4045 Natural Language Processing
Domain Specific Text Data Analysis and Processing



### Readme Notice 
Execution of the programs and all relative links mentioned here requires the change of your current directory to the `SourceCode` folder. Do this with the following command in `command prompt`.
```
  $ cd SourceCode
```



## Version information
- Python 3.6



## Contents
- [Placing dataset files](#placing-dataset-files)
- [Project Installation Guide](#project-installation-guide)
- [Usage guide (Sample Outputs)](#usage-guide)
  - [Choose any domain](#1-choose-any-domain)
  - [Review Pair Ranker](#2-review-pair-ranker)
  - [Sentiment Analysis](#3-sentiment-analysis)


## Placing dataset files
The review dataset file are omitted to save space in project directory. Please place your `CellPhoneReview.json` dataset file in the `dataset/` folder.

## Project Installation Guide
Project setup is as simple as the following 2 steps
#### 1. Install package requirements
The following command will install the required python packages.
```
$ pip install -r requirements.txt
```

#### 2. Download NLTK models (Edit)
The following NLTK models need to be downloaded to run some of the features provided by the `NLTK` i.e. `pos tagging`. Run the following codes on a python interpreter.
```
>>> import nltk
>>> nltk.download('vader_lexicon')
```

## Usage guide
This section describes the steps or commands needed for running the code that solves the problems listed in the project assignment. Please ensure the `CellPhoneReview.json` has been placed in the `dataset/` folder before using any of the commands.

### 1. Choose Any Domain
Execute the following command in `command prompt` to start Dataset Analysis. A trace sample is available [here](SourceCode/results/dataset_analysis/trace.txt)
```
$ python main.py analysis
``` 
The followings are the actual sample trace and graph outputs you would see when running the above command.
```
Top 10 products with most reviews:
B005SUHPO6    836
B0042FV2SI    690
B008OHNZI0    657
B009RXU59C    634
B000S5Q9CA    627
B008DJIIG8    510
B0090YGJ4I    448
B009A5204K    434
B00BT7RAPG    431
B0015RB39O    424
Name: asin, dtype: int64
```

**Sample Sentence Lengths**
```
,asin,overall,reviewText,reviewTime,reviewerID,summary,unixReviewTime,sentencelength
43527,B004Z9W4B0,4,"the product is nice, cute, but not as i expected ...i think there are nicer stuff out there that you can choose form","07 27, 2012",AQIGD6RKS9OJX,"Cute but not as expected",1343347200,1
96469,B008CZO7OU,5,"This was a gift for the father-in-law & he's not always easy to please.  As always Seidio does a great job.  The case is slim, buttons press easily & it looks great as well as protects.","02 6, 2013",A1S48ANGFTOCM9,"Great case.",1360108800,3
55198,B005LFXBJG,4,"I have these plugged in all over my house and never had a problem with them. I like to get OEM chargers because they seem to last longer than knockoffs.","06 20, 2013",A2L9DBKBXLGHOL,"Never have enough",1371686400,2

```

**Top 20 most frequent words**
```
Top 20 most frequent words before stemming:
 [('phone', 174958), ('case', 146050), ('one', 86759), ('like', 71853), ('great', 66874), ('would', 66809), ('use', 61676), ('screen', 60145), ('good', 58601), ('battery', 57976), ('well', 51149), ('iphone', 47691), ('get', 46380), ('charge', 44897), ('charger', 38646), ('product', 38223), ('really', 38055), ('also', 37145), ('time', 36661), ('works', 32743)]

Top 20 most frequent words after stemming:
 [('phone', 192494), ('case', 165228), ('use', 118087), ('one', 92736), ('charg', 92539), ('like', 79743), ('work', 76325), ('great', 66912), ('would', 66814), ('batteri', 66237), ('screen', 61812), ('get', 61243), ('good', 58823), ('look', 52093), ('well', 51161), ('iphon', 50521), ('fit', 50296), ('time', 48381), ('charger', 45281), ('protect', 44734)]
```
**POS Tagging**
```
POS Tagging for 5 random sentences: 
it looked good but did not fit properly the volume would change without touching the buttons and the vibrate switch was partially covered buy a different bumper they are all much better => [('it', 'PRP'), ('looked', 'VBD'), ('good', 'JJ'), ('but', 'CC'), ('did', 'VBD'), ('not', 'RB'), ('fit', 'VB'), ('properly', 'RB'), ('the', 'DT'), ('volume', 'NN'), ('would', 'MD'), ('change', 'VB'), ('without', 'IN'), ('touching', 'VBG'), ('the', 'DT'), ('buttons', 'NNS'), ('and', 'CC'), ('the', 'DT'), ('vibrate', 'NN'), ('switch', 'NN'), ('was', 'VBD'), ('partially', 'RB'), ('covered', 'VBN'), ('buy', 'VB'), ('a', 'DT'), ('different', 'JJ'), ('bumper', 'NN'), ('they', 'PRP'), ('are', 'VBP'), ('all', 'DT'), ('much', 'RB'), ('better', 'JJR')]

```

In addition, the following shows the graph plot for frequency statistics of sentence segmentation, tokenized word without stemming, and tokenized word with stemming. This graph will be available as `.png` image in the folder [here](SourceCode/results/dataset_analysis/) once the program finish running.
![alt text](SourceCode/results/dataset_analysis/graph_result.png)


### 2. Review Pair Ranker
Execute the following command in `command prompt` to start generating the top 20 most frequent noun phrase.
```
$ python main.py nounphrase
``` 
A trace sample is available [here](SourceCode/results/noun_phrase_summarizer/trace.txt). In our experiment, we ran the program using two different types of taggers. The final one used will be the RegExp Parser which is the default mode. If you wish to run it with the ConsecutiveNPChunk tagger simply uncomment the line which sets the mode to "chunktagger". 

### 3. Sentiment Analysis
Execute the following command in `command prompt` to start generating the top 20 positive and negative words.
```
$ python main.py sentiment
``` 
A trace sample and graph image of the result can be found in the folder [here](SourceCode/results/sentiment_word_detection/). Please note that for the `trace.txt` the actual console output will differ somewhat as the file does not include console output for printing progress such as `1000 of 190,000 done`.

The following image shows the actual sample trace and graph output you would see when running the `sentiment word detection` algorithm. The sample trace shows the top 20 positive and negative words along with the calculation of its `adjusted sentiment` value. 

![alt text](SourceCode/results/sentiment_word_detection/result.png)
``` 
