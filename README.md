# CHATQA-bot

This is a RAG system to answer the question according to the dataset you have uploaded according to llm-zoomcamp

In the evaluation part, we assess the quality of our entire RAG
system before it goes live.

In the monitoring part, we collect, store and visualize
metrics to assess the answer quality of a deployed LLM. We also
collect chat history and user feedback.

# Quick start

To run the app, first you need to set your openai key in `prep.py`, then pull the docker images, using:

```python
cd app
pip install -r requirement.txt
docker-compose up
```

After everything is done, you need to pull `ollama-phi3`:

```python
docker exec -it ollama bash
> ollama pull phi3
> exit

#  or this way
docker-compose exec ollama ollama pull phi3
```

Then you are prepared.

```python
python prep.py
```

When you just want to init the database, not for index the data, you can comment from `<start>` to `<end>` in the `prep.py`.

Then you can check the details in database using:

```python
pgcli -h localhost -U your_username -d course_assistant -W
# password is in .env 'POSTGRES_PASSWORD'

\l # to see the list of database
\c course_assistant 
\dt # to see the table

# ctrl+d to exit
```

Now you can use the streamlit to use.

You can also use grafana to monitor the llm, before you run it, you can run

```python
python generate_data.py
```

to pretend many questions are save in database.



### Overview of the module

![image](https://github.com/user-attachments/assets/0c5e932b-4fca-4d51-8b1c-93f4600861dc)


