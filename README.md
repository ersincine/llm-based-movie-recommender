# LLM-based Movie Recommender

Download personal movie ratings, their overall ratings and some of the metadata for these movies from IMDb. Split movies into train and test sets. (There will be no real training. Only few-shot learning. That's why the train set can be small. But we need to repeat the experiments.)

(This is not exactly a recommender. It will predict how much you will like a given movie.)

## Models

Try multiple models:

- Simple models:

  - Base model 1: Prediction is the same as overall rating
  - Base model 2: Prediction is the average of my ratings

- LLM-based models:

  - Give titles of the movies, my personal ratings and overall ratings. (Rely on LLM's knowledge of the movies.)
  - Also give metadata (year, genre etc.).

Parameters:

- Very low temperature.
- Use gpt-3.5-turbo for a reduced cost.

## Evaluation

Test:

- For each inference, ask a single movie. The error is the mean squared error.

Assume there are 100 movies. Try 20-shot learning:

- Ask the question 10 times. (We can ask 80 question but we need to reduce the costs)
- Repeat this 10 times for different set of given examples.

## Future Work

- Different models:

  - Also give synopsys.
  - Also give the reviews.

- Motivate the LLM:

  - "You are a movie expert", "Take a deep breath", "I will give you $100" etc.

- Different task description:

  - Instead of "Predict my rating for this movie", something like "Guess my opinion about this movie and predict my rating at the end".

- Maybe try different number of examples in the future.
- Maybe try larger models in the future.
