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

## 4.6 Capturing user feedback

<a href="https://www.youtube.com/watch?v=XapKKBUMQ4M&list=PL3MmuxUbc_hIB4fSqLy_0AfTjVLpgjV3R">
  <img src="https://markdown-videos-api.jorgenkh.no/youtube/XapKKBUMQ4M">
</a>

> You can see the prompts and the output from claude [here](code.md)

Content

* Adding +1 and -1 buttons
* Setting up a postgres database
* Putting everything in docker compose

```bash
pip install pgcli
pgcli -h localhost -U your_username -d course_assistant -W
```


Links:

* [final code](app/)
* [intermediate code from claude](code.md#46-capturing-user-feedback)


### 4.6.2 Capturing user feedback: part 2 

<a href="https://www.youtube.com/watch?v=BG8MlbidatA&list=PL3MmuxUbc_hIB4fSqLy_0AfTjVLpgjV3R">
  <img src="https://markdown-videos-api.jorgenkh.no/youtube/BG8MlbidatA">
</a>

* adding vector search
* adding OpenAI

Links:

* [final code](app/)
* [intermediate code from claude](code.md#462-capturing-user-feedback-part-2)


## 4.7 Monitoring the system

<a href="https://www.youtube.com/watch?v=BQN0TOi2Rew&list=PL3MmuxUbc_hIB4fSqLy_0AfTjVLpgjV3R">
  <img src="https://markdown-videos-api.jorgenkh.no/youtube/BQN0TOi2Rew">
</a>

* Setting up Grafana
* Tokens and costs
* QA relevance
* User feedback
* Other metrics

Links:

* [final code](app/)
* [SQL queries for Grafana](grafana.md)
* [intermediate code from claude](code.md#47-monitoring)

### 4.7.2 Extra Grafana video

<a href="https://www.youtube.com/watch?v=qGFAX5ra1G8&list=PL3MmuxUbc_hIB4fSqLy_0AfTjVLpgjV3R">
  <img src="https://markdown-videos-api.jorgenkh.no/youtube/qGFAX5ra1G8">
</a>

* Grafana variables
* Exporting and importing dashboards

Links:

* [SQL queries for Grafana](grafana.md)
* [Grafana dashboard](dashboard.json)

## Homework

See [here](../cohorts/2024/04-monitoring/homework.md)


## Extra resources

### Overview of the module

![image](https://github.com/user-attachments/assets/0c5e932b-4fca-4d51-8b1c-93f4600861dc)


