# TFIDF

Calculate TFIDF (Term Frequency Inverse Document Frequency) for language learning, following the approach outlined by the YouTube Channel [One Word At A Time](https://www.youtube.com/@OneWordataTime1) in their video, [What to do when language rushes by](https://www.youtube.com/watch?v=hJyJ7DLmSfQ).

Before you read or watch something in your target language, it is often useful to know what vocabulary you should learn beforehand to understand that content. 

One simple approach is to create a list of words in that content sorted by frequency of appearance, and then making sure to learn the words that are most common in that text. That can be a fine approach, but there are often words in the text that aren't high in frequency, but yet are still very important to learn because they may be uniquely key to the meaning of that text. 

TFIDF is a metric that attempts to surface which words might be relatively low frequency in the text, but high importance for understanding the meaning of the text. It works by assigning a score for each word, where the score is highest if that word simultaneously

* Appears frequently in the content that you are about to consume
* AND, does NOT frequently appear in other typical content

The logic is that if a word is common in one piece of content, but not common in other pieces of content, that it might have unique importance in the context of the target content. 

The YouTube video does a much better job of explaining, so please view that. 

<br>

# How the tool works

The tool calculates TFIDF using the same formula outlined in the video: <br><br>

```math
\left( \# \ mentions\ in\ target \ media \right) * ln\left( \frac{total\ \# \ of \ other \ media \ documents }{\# \ of \ other \ media \ documents \ containing \ word}\right)
```
<br><br>
There are a few sample files / directories provided in the repository. These are all Mandarin Chinese, but should work for other languages.

* **`Sample_Input_Media_To_Process.srt`:** This is the target media that you are about to consume, which contains all of the words that you want to calculate TFDIF for. This sample is an SRT subtitles file, but the tool also accepts .txt, and .docx. 

* **`Sample_Corpus`:** This the "other media documents" referenced in the formula. When calculating TFIDF, the tool will look through to see how often a word appears in these files as well. If the word does not appear commonly in this content, TFIDF will tend to be higher because the tool assumes the word in question is not super common in content outside of the target media. This folder can contain files with format .srt, .txt, or .docx.

* **`Sample_Output.xlsx`:** This is a sample output file from the tool, which contains all of the words in the target content, and a bunch of data calculated for each word such as frequency of appearance, and TFIDF score. By default, it will be sorted by decreasing TFIDF score.

* **`Sample_Known_Words.txt`:** This is a list of words that you already know, and thus don't need to calculate TFIDF for. If you don't have a list of words that you already know, you can leave this file blank.


The tool will go through each word in `Sample_Input_Media_To_Process.srt`, and calculate TFIDF using the media in the folder `Sample_Corpus` as the set of "other media documents" for comparision. If it encounters a word in `Sample_Known_Words.txt`, it will exclude it from the analysis given the user already knows that word. It will then output everything into `Sample_Output.xlsx`. 

<br>

# How to use

At at this time, I have not written any GUI or command line interface. So to use the tool, you will have to run the Python file directly (e.g., open a terminal window in the folder, and run `python TFIDF.py`)

You will just need to replace my sample input files with your own. Each of the input / output document names are declared as global variables at the top of the script, so you can edit directly there. 

<br>

# Known issues

So far, this script has only been tested with Mandarin Chinese, using Simplified Characters. The script may fail entirely for other languages, especially those that have conjugations / cases. My hope is that by looking at the source code, you can modify for your given language.

<br>

# Interested in learning more?

Feel free to visit my YouTube channel [Joshua Lykes](https://www.youtube.com/@jlykes) where I cover language learning, as well as many other topics. One video that mmight be of special interest to users of this tool is [I'm learning Chinese by watching TV & Movies! 1 year udpate and my COMPLETE approach](https://youtu.be/xf_TvlGaYfQ?si=LfoVyqHYMp0oOFiz).