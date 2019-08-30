# FluencySimilarity

Contains various scripts for the analysis of transcripts of second language learners of english. These are scripts for Nel de Jong.

Included in this repo are scripts to compute the Jaccard similarity and cosine similarity of tf-idf vectors. This can be computed when the tokens are words or trigrams. See below for more details on SimilarityAnalysis. 
### How do I get set up? ###

* SimilarityAnalysis.bat is batch file that runs on sample data
* To list options for the scripts use the command python <path-to-script> --help
* Outputs from SimilarityAnalysis.bat are in the output folder in root of the repository.
* Dependencies: Uses interpreter version Python 3 and NOT Python 2.7, third party libraries are in the requirement.txt file
* How to run tests: Install PyCharm IDE and configure paths to resolve dependencies within each project. Once this is done you should be able to run the unit tests in PyCharm.

### Deployment instructions ###
1. Install Python 3
2. Clone or download the entire repository and unzip
3. Running SimilarityAnalysis.bat and SimilarityAnalysisPst.bat will run on test data.
4. To run on other data modify the input file paths in batch file to point to new input files.

To see help from the command line run the command

$ python "src\SimilarityAnalysis.py" -h

### Examples

Ex1) Similarity based on trigrams

$ python "src\SimilarityAnalysis.py" -t trigram -d "sampledata1_out" > "sampledata1_out\result.csv"

Ex2) Similarity based on POS trigrams

$ python "SimilarityAnalysis\src\SimilarityAnalysis.py" -t trigram -d "sampledata1_out" > "sampledata1_out\result.csv"

### Documentation of SimilarityAnalysis

To understand how Similarity in SimilarityAnalysis is computed one should start by running and inspecting the unit tests in SimpleTests.py. These tests should give a basic understanding of what this core of the code does. The other code in this  is mainly for performance and unpacking the data from the form it is in so that we can compute the similarity (i.e., plumbing)

The raw methods that compute the compute the Jaccard Similarity and Cosine Similarity are in IRSystemHelper.py. IRSystem.py and IRSystemSimple.py are wrapper classes around methods of this class that adds caching for performance and methods to read files from disk. If you want to understand how these basic methods can be used, look at SimpleTests.py. Here there are unit tests that set up very simple test documents and compute all the desired similarities.

### Who do I talk to? ###

* admin: phil.tillman@gmail.com
* researcher: c.a.m.dejong@uva.nl

### Publishing using our code ###
Please cite our paper if you use this code:

de Jong, N., & Tillman, P. C. (2018). Grammatical structures and oral fluency in immediate task repetition: trigrams across repeated performances. In M. Bygate (Ed.), Learning language through task repetition (pp. 43-73). Amsterdam: John Benjamins.

```
@article{deJongTillman2018,
  title={ Grammatical structures and oral fluency in immediate task repetition: trigrams across repeated performances},
  author={de Jong, N., & Tillman, P. C.},
  journal={Learning language through task repetition},
  editor={M. Bygate},
  publisher={John Benjamins},
  location={Amsterdam},
  year={2018}
}
```

### License ###
Copyright 2019 Philip Tillman

Licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0.html) (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.