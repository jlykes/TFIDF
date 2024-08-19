# TFIDF

Calculate TFIDF for language learning, following the approach outlined by the YouTube Channel [One Word At A Time](https://www.youtube.com/@OneWordataTime1) in their video, [What to do when language rushes by](https://www.youtube.com/watch?v=hJyJ7DLmSfQ).

Before you read or watch something in your target language, it is often useful to know what vocabulary you should learn beforehand to understand that content. 

One simple approach is to create a list of words in that content sorted by frequency of appearance, and then making sure to learn the words that are most common in that text. That can be a fine approach, but there are often words in the text that aren't high in frequency, but yet are still very important to learn because they may be uniquely key to the meaning of that text. 

TFIDF is a metric that attempts to surface which words might be relatively low frequency in the text, but high importance for understanding the meaning of the text. It works by assigning a score for each word, where the score is highest if that word simultaneously

* Appears frequently in the content that you are about to consume
* AND, does NOT frequently appear in other typical content

The logic is that if a word is common in one piece of content, but not common in other pieces of content, that it might have unique importance in the context of the target content. 

The YouTube video does a much better job of explaining, so please view that. 


# How the tool works

The tool calculate TFIDF using the same formula outlined in the video: 

```math
\left( right)
```


# How to use

To be written


# Known issues

So far, this script has only been tested with Mandarin Chinese, using Simplified Characters. The script may fail entirely for other languages, especially those that have conjugations / cases. My hope is that by looking at the source code, you can modify for your given language.


# Interest in learning more?

Feel free to visit my YouTube channel [Joshua Lykes](https://www.youtube.com/@jlykes) where I cover language learning, as well as many other topics. One video that mmight be of special interest to users of this tool is [I'm learning Chinese by watching TV & Movies! 1 year udpate and my COMPLETE approach](https://youtu.be/xf_TvlGaYfQ?si=LfoVyqHYMp0oOFiz).