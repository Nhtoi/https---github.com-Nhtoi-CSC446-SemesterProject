CHALLENGES:
 [] HOW TO EXTRACT INFORMATION FROM WEBSITE
 [] CLEAN THE DATA, NO URL’S, SPECIAL CHARACTERS ETC
 [] TRAIN AI (BERTSUM AND PYTORCH)
 [] BUILD FRONT-END (FOR EXTRA POINTS/WOW-FACTOR I ASSUME)


HOW TO EXTRACT INFORMATION FROM WEBSITES	

Using selenium to extract information from the website, since the website can be chosen by 
driver = webdriver.Firefox()
driver.get("http://www.python.org")
Can add variable “webiste” which stores user input website and can be fed to 
Website = user input
driver.get(website)
Can extract from website elements more information here: 
https://selenium-python.readthedocs.io/locating-elements.html
For our training we need to extract upvotes, comments, anything really that can indicate a good comment and helpful for our summarization.

Could be a google chrome plugin, that can communicate with a python backend
Data can be stored in prostresql probably to easily extract upvotes, etc…

CLEAN DATA

From our first assignment we learned how to clean data basically, so using NLKT https://www.nltk.org/  for lemmatization, spacy  https://spacy.io/ for tokenization and some sort of text normalization sklearn
(https://www.digitalocean.com/community/tutorials/normalize-data-in-python).
Basically first step is to make words like car, cars, car’s into one car, that is lemmatization, tokenization is separating these words, then a very time consuming part would be annotating the data in order to be able to train our model correctly. However we can use Distant Supervision where we just accept highly upvoted comments, or comments with a lot of replies etc…. 


TRAIN AI


Since we have other things to do and we don’t want to spend too much time training/annotating data we are going to generate weak labels using heuristics, there are three options for this, one we use the upvotes and stuff I mentioned earlier to allow a weather a sentence (discussion post) goes thru or not. The other is we us https://pypi.org/project/pytextrank/ were if  the sentences of posts are repeated throughout the discussion it will assume that it is of importance, and another way is using repeated words throughout the post, we then grab a sentence for example if all of these agree that the sentence/comment is valuable we keep it in for training We can also review a couple of them ourselves but honestly I don’t want to.


FRONT END (optional)

Make a Chrome plugin which grabs the website you're in, feeds it to our model in the back end and then summarizes it for the user, which then is displayed back in the front-end. 
