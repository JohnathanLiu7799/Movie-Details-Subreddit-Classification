
# Classifying Subreddit Posts

Subreddits are communities built around a certain topic on Reddit.com where users can comment on other posts or add posts of their own.
These can include text, images, and video among other media. 
We aim to be able to create a model that can classify reddit posts into different subreddits using their title.



## Problem Statement

How good of a model can we create to differentiate between posts from 

- r/MovieDetails
- r/ShittyMovieDetails

In the interest of understanding ironic and sarcastic speech intended to imitate 
more genuine content. This is the first step in a longer process and should be understood as such.

When done succesfully, this can be used by companies to better understand online sentiments,
many of which are buried under layers of irony, especially in today's online culture.

We will be optimizing for accuracy as there is no substantial difference between a 
type I or type II error in this case.


## Data Dictionary

| Feature   	| Description                                                                        	|
|-----------	|------------------------------------------------------------------------------------	|
| Title     	| Title of the post                                                                  	|
| Subreddit 	| Subreddit of the post, 1 if r/ShittyMovieDetails 0 if r/MovieDetails 	                |

## Analysis Summary

After running through several models we found some limitations.

Due to hardware restrictions, we did not have enough data to properly use an XGBoost or a Neural Network

There were many words that existed in both, simply due to how integrated they were with pop culture such as the Marvel
Cinematic Universe of Disney's Star Wars.

That being said our best performing model was Logistic Regression with an accuracy of 81%.
Another benefit of Logistic Regression is that we can return some coefficients with words,
the coefficients in this case being indicative of how likely a word is to determine whether a 
title is from one reddit or another. 

The top 25 for each subreddit were:
| r/ShittyMovieDetails 	| r/MovieDetails 	|
|----------------------	|----------------	|
| 'fact',              	| 'noticed',     	|
| 'because',           	| 'comments',    	|
| 'subtle',            	| '1998',        	|
| 'title',             	| 'similar',     	|
| 'shit',              	| '1987',        	|
| 'fucking',           	| 'shirt',       	|
| 'despite',           	| '1983',        	|
| 'role',              	| 'credits',     	|
| 'audience',          	| 'comics',      	|
| 'cast',              	| '2018',        	|
| 'this',              	| 'throughout',  	|
| 'hours',             	| 'plate',       	|
| 'franchise',         	| '1990',        	|
| 'actors',            	| 'opening',     	|
| 'actor',             	| 'when',        	|
| 'shitty',            	| 'during',      	|
| 'nothing',           	| '2017',        	|
| 'sequel',            	| 'amp',         	|
| 'titanic',           	| 'else',        	|
| 'filming',           	| 'across',      	|
| 'us',                	| 'behind',      	|
| 'movie',             	| 'two',         	|
| 'means',             	| 'hand',        	|
| 'protagonist',       	| 'shot',        	|
| 'actually'           	| '2003'         	|

We can draw some clear takeways including:

- r/MovieDetails will tend to talk more about older movies, mentioning yearas like 1998, 1990, 2003 etc.
- r/ShittyMovieDetails will often use swears like 'fucking','shit', and 'shitty' for comedic or dramatic effect.


## Conclusion

In conclusion while there are clear differences between these two subreddits in their sentiments,
we have created a Logistic Regression model that can accurately identifiy where a post comes from 81% of the time.

While this is great as a start, the artificial division of subreddits creates an unrealistic standard
for pushing into other environments or platforms where genuine and ingenuine sentiments will be mixed.

Going forward, it is critical we:

- Expand The Dataset: We only used 14k posts due to technical limiations and even fewer after cleaning. More posts could lead to more insight and a better model as well as differenttypes of models we currently cannot use.

- Weighing Posts by Score: On many platforms there are ways to support a post whether it be Reddit's upvote or Meta and Twitter's likes. By weighing posts with such metrics instead of just by recency, we might be able to target the spirit of these sentiments much more accurately.

- Apply in New Environments: A final step for this project, being applicable in more platforms, such as Instagram, Meta, Twitter, etc. where the large proportion of consumer sentiments lie.

## Acknowledgements

 - [r/ShittyMovieDetails](https://www.reddit.com/r/shittymoviedetails/)
 - [r/MovieDetails](https://www.reddit.com/r/MovieDetails/top/?t=all) 
 - [PushShift API](https://github.com/pushshift/api) 

 
 
