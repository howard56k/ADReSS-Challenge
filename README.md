# Evaluating Acoustic and Linguistic Features for Neurological Task Score Prediction for Alzheimer’s


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#extraction">Feature Extraction</a></li>
    <li><a href="#selection">Feature Selection</a></li>
    <li><a href="#training">Training</a></li>
    <li><a href="#testing">Testing</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

 The average life expectancy is increasing globally due to advancements in medical technology, preventive health care, and a growing emphasis on gerontological health. Therefore, developing technologies that detect and track aging-associated disease in cognitive function among older adult populations is imperative. In particular, research related to automatic detection and evaluation of Alzheimer's disease (AD) is critical given the disease's prevalence and the cost of current methods. As AD impacts the acoustics of speech and vocabulary, natural language processing and machine learning provide promising techniques for reliably detecting AD. We compare and contrast the performance of ten linear regression models for predicting Mini-Mental Status Exam scores on the ADReSS challenge dataset. We extracted 13000+ handcrafted and learned features that capture linguistic and acoustic phenomena. Using a subset of 54 top features selected by two methods: (1) recursive elimination and (2) correlation scores, we outperform a state-of-the-art baseline for the same task. Upon scoring and evaluating the statistical significance of each of the selected subset of features for each model, we find that, for the given task, only handcrafted linguistic features are significant while acoustic and learned features are not.



<!-- GETTING STARTED -->
## Getting Started

You will need to download the Feature Extraction tools, Install Package Requirements

### Prerequisites

Get Text Feature Extraction Tools from [NLP TOOLS FOR THE SOCIAL SCIENCES](https://www.linguisticanalysistools.org/) This includes [CLA](https://www.linguisticanalysistools.org/cla.html) , [ARTE](https://www.linguisticanalysistools.org/arte.html) , [TASSC](https://www.linguisticanalysistools.org/taassc.html) , [SEANCE](https://www.linguisticanalysistools.org/seance.html) , [Sinlp](https://www.linguisticanalysistools.org/sinlp.html) , [Taaco](https://www.linguisticanalysistools.org/taaco.html) , and [Taales](https://www.linguisticanalysistools.org/taales.html)


### Installation

Package Prerequisites
   ```sh
   pip install -r requirements.txt
   ```
 Install Disvoice
  ```sh
   git clone https://github.com/jcvasquezc/DisVoice
   ```

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Extraction

Audio Extraction Is done by using [pyAudioAnalysis](https://github.com/tyiannak/pyAudioAnalysis) and [DisVoice](https://github.com/jcvasquezc/DisVoice)

Text Extraction is Done by [CLA](https://www.linguisticanalysistools.org/cla.html) , [ARTE](https://www.linguisticanalysistools.org/arte.html) , [TASSC](https://www.linguisticanalysistools.org/taassc.html) , [SEANCE](https://www.linguisticanalysistools.org/seance.html) , [Sinlp](https://www.linguisticanalysistools.org/sinlp.html) , [Taaco](https://www.linguisticanalysistools.org/taaco.html) , and [Taales](https://www.linguisticanalysistools.org/taales.html)

For audio extraction you would run the first block of Code in the JupyterNote book file labeled "Audio Feature Extraction" and You will get the PyAudioAnalysis Features
Then For disvoice for Articulation for an example you will have to follow the steps in their repo; where it would look something like this:
```sh
python articulation.py <file_or_folder_audio> <file_features> <static (true or false)> <plots (true or false)> <format (csv, txt, npy, kaldi, torch)>
```
Then for text extraction Download all the tools and follow the steps on each of their links and Use the Text folder as folder for it to extract from
You would then take all the CSVs produced from text extraction and combine them and put it into a dataframe with the Audio Features

<p align="right">(<a href="#top">back to top</a>)</p>






<!-- USAGE EXAMPLES -->
## Selection

Selection is done through 2 different methods of SelectKBest by correlation and RFECV.
You will pass the DataFrame gathered from the extraction phase to the Each of the extraction methods and it will return top 100 features from each of them.


<p align="right">(<a href="#top">back to top</a>)</p>





<!-- USAGE EXAMPLES -->
## Training

Utilize the Training Block in the Final Jupyter Note File where you would pass the top 100 features of each and it will train 2 different sets of models based on Correlation and RFECV

<p align="right">(<a href="#top">back to top</a>)</p>






<!-- USAGE EXAMPLES -->
## Testing

Lastly Testing is Done alongside the Training Where after the model is done training it is then tested on the test set. You will be able to further test the Model and Graph the results in the next blocks of the code.

<p align="right">(<a href="#top">back to top</a>)</p>




