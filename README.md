### Setup instructions
- This project uses `poetry` to manage dependencies
- Install the `poetry` package manager
- navigate to the project folder and run `poetry install` to install required packages and initialize a virtual enviroment
- open the notebook and run all the cells

### Dataset source and preprocessing description
The dataset preprocessing was as follows (in sequence):
- Tokenization
- Stop word removal
- Lemmatization

### Agent design
#### Scenario
- Trending News Agent that provides information about some of the latest and hotest topics

#### Goal
 - The goal of the agent is the keep the user up to date with the latest and hotest topic to help them stay up to date always

#### Tools
- Any news article is first preprocessed using the utility function `preprocess_text` to tokenize, remove noise (stop words) and then lemmatize the text
- The articles are then grouped into categories word frequencies

#### Reasoning
- Queries are passed to the ChatGPT LLM using an API to categories the query into one of a fixed number of options
- The processed query is then passed through to the agent which is equiped with a set of functions for handling each query
- The agent parses the corpus and groups the various news articles into categories.
- Based on the user's selected category, a number (specified by the user) of the latest articles in a given category are returned
