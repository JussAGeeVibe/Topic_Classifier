# Topic_Classifier

Use Case Summary
Random Forest classifier for news topics.


Front End:

Load in the Flask .py file to their internet enabled device. 
Feed in textual data for classification. For optimal results textual data should be at least two sentences long.
Click the 'Predict' button to predict the classification. 


Back End:

Textual data is processed by means of:

      Removing punctuation
      Removing digits
      Removing special characters
      Removing text formatting
      Removing stopwords
          Via the SpaCy Python library
      Lemmatizing words
          Via the SpaCy Python library
      
      
Cleaned and processed textual information:

      Textual data fed into a pipeline. Pipeline consists of...
      Assigning a numerical statistic based on TF-IDF Vectorization
      Statistical vectors passed onto a Random Forest Classifier for classification
      
      
Output:

      Classification of the textual input is returned for one of seven classification topics.
            Economy
            Education
            Entertainment
            Environment
            Health
            Sports
            Technology
            
User repeats process for any additional textual data to be categorized. 



Back back end:

Data Acquisition for Training
      Utilized BeautifulSoup and UrlLib libraries to scrape links and raw HTML textual data of articles.
            Removed all HTML meta-data and embedded hyperlinks
            Removed punctuation
            Removed digits
            Removed special characters
            Removed any text formatting
            Removed stopwords
                Via the SpaCy Python library
            Lemmatized words
                Via the SpaCy Python library
                
            Article topics balanced for equal representation of each topic category.
            Dataset split into train_val dataset and test set.
                Model trained after splitting train_val dataset with a 25% split.
                    Training consist of 1,050 articles
                    Validation for model tuning consist of 350 articles.
                    Test set consist of 210 articles. 
                
      Categorized using the 'h3' header tag that accompanied the article during the scrape. 
            Put into a pandas dataframe for organization. 
            
      Summarized the articles to condense feature space:
            Summarization perform using the Gensim.summarizaton library.
            Built on top of the TextRank algorithm that ranks the importance of sentences. 
      
      Summaries fed into pipeline:
            Summarized articles fed into TF-IDF vectororizer.
            Vectorized given to Random Forest to learn key buzzwords for classification.
            
      Model trained on 1050 articles.
      Model validated and tuned on 350 articles.
      Model tested on 210 articles.

      Performace evaluated using accuracy and F1 score.
      Model performed with 80% and 80% F1 score for the test data.
