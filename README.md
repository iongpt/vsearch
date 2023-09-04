# vsearch
Full text search your data using vector search

- Chunk based on sentence / paragraph at 512 tokens. Use sliding window
- Use llama 2 fine tune to rephrase the chunks in 4 different ways
- tokenize with RoBERTa based on semantic meaning
- add general context to each chunk (for example the chapter/section title or description)
- use fine tuned llama 2 to generate the embeddings based on the tokeks from RoBERTa
- generate / enrich any additional metdata (page, link, etc)
- store in local ChromaDB the embedings and metadata in local / cloud ES
- fine tune llama 2 16k with RoPE model to respond "I am not familiar with the subject" if the embeddings does not contain enough information
- when doing inference, tokenize the question, do the vector search, fetch the embeddings and metadata
- If there are not enough matchin embeddings, rephrase the question
- Create the prompt and add the embeddings to the context and do the inference
- If there is a response, enrich it with the metadata and return it to the user
