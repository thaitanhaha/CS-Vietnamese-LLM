# CS Vietnamese LLM

In this project, I finetune `Llama-3.2-1B-Instruct-bnb-4bit` to answer questions related to computer science topic.

### Dataset

The `5CD-AI/Vietnamese-Multi-turn-Chat-Alpaca` dataset, which is available on Huggingface, is used during the training phase.

I also use a simple keyword-matching algorithm to create a CS-related training set. 

About the CS-related testing set (the csv file), the questions and answers are supported by [`chatgpt`](https://chatgpt.com/).

### Training

I use 3 training-testing experiments, with `Low-Rank Adaptation` technique.
- `1` Using a general system instruction, train with general dataset. 
- `2` Using a CS-related system instruction, train with general dataset. 
- `3` Using a CS-related system instruction, train with CS-related training set. 
- and all test with CS-related testing set.

### Testing

For **Qualitative** evaluation, it can be supposed that the experiment `3` gives the best results, focusing on the field of computer science. However, it is sometimes *shorter* than experiment `1` and `2`. 

For **Qualitative** evaluation, the `bert-score` library is used. The heatmap of score also illustrates that the experiment `3` gives best results, while the other two experiments yield competitive results, neither truly outperforms the other.


![__results___6_5](https://github.com/user-attachments/assets/0d82a82d-1d0a-4582-a29a-c98678b8ab77)









