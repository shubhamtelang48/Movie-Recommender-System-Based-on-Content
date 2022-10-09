# Movie-Recommender-System-Based-on-Content


Recommender System is a system that seeks to predict or filter preferences according to the user’s choices.
Recommender systems are utilized in a variety of areas including movies, music, news, books, research articles, search queries, social tags, and products in general. 
Recommender systems produce a list of recommendations in any of the two ways – 
- Collaborative filtering: Collaborative filtering approaches build a model from the user’s past behavior (i.e. items purchased or searched by the user) as well as     similar decisions made by other users. This model is then used to predict items (or ratings for items) that users may have an interest in.
- Content-based filtering: Content-based filtering approaches uses a series of discrete characteristics of an item in order to recommend additional items with similar properties. Content-based filtering methods are totally based on a description of the item and a profile of the user’s preferences. It recommends items based on the user’s past preferences.

In this project we are working on content-based filtering model on movies datasets.This dataset we collect from kaggle and with the help of pandas library we read it on our jupyter notebook.
Their are two dataset we collect from kaggle in which movies dataset have budget,genres,language,title,keywords,overview,etc columns and credits dataset have movie_id,title,cast and crew columns presents.Then we merge this two dataset into one on title column for our purpose.
After merge we only need seven features for our model to recommends such as [title,movie id,genres,keywords,cast,overview and crew].
Now we cleaned the dataset by finding if any null value or any outlier is present in it or not, if yes then either we delete that row or empute it with most frequent value.
- Their are lots of cast present in cast column but we choose only top three cast for our system to reduce time and data redundancy.
- We do a feature engineering on keywords and genres column so we only get our requred result in the list.In genres column we don't need id only we need the name of genres and same with keywords column.
- In crew feature we only want the directer name so by using function fetch the name in the list.
- Overview column is in string format so we have convert it into list.
- After this we convert overview,genres,keywords,cast and crew columns into single column called tags.Then again we convert the list into string format for analysis.
- Then we use NLTK library for analyize the tags column and do the count Vectorization on it.
- At the end we use cosine_similarity function to find the similar movies for recommendation.
- Then we create a function which gives us the top five similar movies.
   
   def recommend(movie):
    index = new_df[new_df['title'] == movie].index[0]
    distances = sorted(list(enumerate(similarity[index])),reverse=True,key = lambda x: x[1])
    for i in distances[1:6]:
        print(new_df.iloc[i[0]].title)
        
        recommend('Avatar')
        output= 
                Titan A.E.
                Small Soldiers
                Ender's Game
                Aliens vs Predator: Requiem
                Independence Day


