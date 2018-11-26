# Suspicious News Detection Using Micro Blog Text

---

## Abstract
We constructed two Japanese datasets based on the method on reference[1], the one for a task **suspicious casting post (SCP) detection** and the other for a task **suspicious article (SA) detection**. SCP is a post on twitter that cast supicion on news articles, and SA is suspicious article to be verified manually. These tasks aims to support human experts to detect suspicious news articles to be verified, which is costly but a crucial step before verifying the truthfulness of the articles.   
  
---

## Specification
Thise datasets do not include tweets text. This is because redistribution of the tweets text is prohibited according to the Twitter API's terms of service. So the datasets users need to obtain tweets data based on `tweet_id_str` field using the Twitter API. Also, it is thought that tweets of the user who became a protected account and the deleted tweets cannot be obtained correctly. Please acknowledge this point.

#### SCP dataset
This dataset is provided in json format. One line is an object representating one tweet.
##### example
```
{
    "tweet_id_str": "XXXXXXXXXXXXXXXXX"     #A string representation of the unique identifier for a Tweet.
    "label": 1                              #A label representing whether this tweet is SCP or not. (This tweet is SCP: "1", This tweets is not SCP: "0")
}
```

#### SA dataset
This dataset is provided in json format. One line is an object representating one article.
##### example
```
{
    "tweets": [                             #List of tweet_id_str fields referring to a specific article.
        "XXXXXXXXXXXXXXXXX",
        "XXXXXXXXXXXXXXXXX",
        "XXXXXXXXXXXXXXXXX",
        "XXXXXXXXXXXXXXXXX",
        "XXXXXXXXXXXXXXXXX"
        ]                             
    "label": 1                              #A label representing whether this article is SCP or not. (This article is SA: "1", This article is not SA: "0")
}
```
---

## Statistics
#### SCP dataset
* &#35; Samples (pos/neg): 7,775 (1,036 / 6,739)
* Avg. Length of Comments: 56.6

#### SA dataset
* &#35; Samples (pos/neg): 1,836 (564 / 1,272)  
* Avg. Length of Comments: 60.4  
* Avg. Tweets / Article: 2.75

---

## Contact
* Please feel free to contact [Tsubasa Tagami](http://www.cl.ecei.tohoku.ac.jp/~tagami/) < tagami at ecei.tohoku.ac.jp > with questions about datasets.
* If you use these datasets, please let me know.

---

## Acknowledgments
* This datasets was constructed with the support by JSPS KAKENHI Grant Number JP15H01702.

---

## References
1. Tsubasa Tagami, Hiroki Ouchi, Hiroki Asano, Kazuaki Hanawa, Kaori Uchiyama, Kaito Suzuki, Kentaro Inui, Atsushi Komiya, Atsuo Fujimura, Hitofumi Yanai, Ryo Yamashita, Akinori Machino. [**Suspicious News Detection Using Micro Blog Text**](https://arxiv.org/abs/1810.11663). In The 32nd Pacific Asia Conference on Language, Information and Computation (PACLIC 32), pages (to appear), December 2018.