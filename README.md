# NLP-Techniques-on-Text-Data
## Theory
This experiment introduces fundamental **Natural Language Processing (NLP)** techniques using the NLTK (Natural Language Toolkit) library in Python. NLP is a field of artificial intelligence that helps computers understand, interpret, and manipulate human language.
The notebook demonstrates the following core NLP techniques on text data:
1. Installing and importing NLTK  
```markdown
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('wordnet')
   nltk.download('averaged_perceptron_tagger')
   ```

2. Tokenization  
   - Word Tokenization: Splitting text into individual words  
     ```python
     from nltk.tokenize import word_tokenize
     tokens = word_tokenize("Natural language processing is interesting")
     ```
   - Sentence Tokenization: Splitting text into sentences  
     ```python
     from nltk.tokenize import sent_tokenize
     sentences = sent_tokenize("Python is easy. It is widely used in data science")
     ```

3. Stop Word Removal  
   Removes common words (is, the, and, in, etc.) that usually carry less meaning.  
   ```python
   from nltk.corpus import stopwords
   stop_words = set(stopwords.words('english'))
   filtered_words = [word for word in words if word.lower() not in stop_words]
   ```

4. Stemming  
   Reduces words to their root form (e.g., playing → play, runs → run). Uses PorterStemmer.  
   ```python
   from nltk.stem import PorterStemmer
   stemmer = PorterStemmer()
   print(stemmer.stem('playing'))   # Output: play
   ```

5. Lemmatization  
   Converts words to their dictionary/base form (lemma) considering context (e.g., buddies → buddy, studies → study). Uses WordNetLemmatizer.  
   ```python
   from nltk.stem import WordNetLemmatizer
   lemmatizer = WordNetLemmatizer()
   print(lemmatizer.lemmatize('studies'))   # Output: study
   ```

6. Part-of-Speech (POS) Tagging  
   Identifies the grammatical role of each word (noun, verb, adjective, etc.).  
   ```python
   from nltk import pos_tag
   pos_tags = pos_tag(word_tokenize("Python is a powerful programming language"))
   ```

7. Word Frequency Count  
   Counts the occurrence of each word in the text.  
   ```python
   from nltk.probability import FreqDist
   freq_dist = FreqDist(words)
   print(freq_dist.most_common())
   ```

These techniques are foundational for:
- Text preprocessing in NLP pipelines
- Sentiment analysis
- Text classification
- Information retrieval
- Building chatbots and language models

## Conclusion

The experiment successfully demonstrated essential NLP techniques using NLTK:
- Tokenization (word and sentence level)
- Stop word removal for cleaning text
- Stemming and Lemmatization for reducing words to root forms
- Part-of-Speech tagging to understand grammatical structure
- Word frequency analysis to understand term importance

Key observations:
- Tokenization breaks raw text into manageable units
- Removing stop words reduces noise and improves focus on meaningful terms
- Lemmatization generally gives better results than stemming because it considers context
- POS tagging helps in understanding the role of words in a sentence
- Frequency distribution is useful for identifying important or repeated terms
