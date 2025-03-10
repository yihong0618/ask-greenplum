# Ask Greenplum Q&A

https://user-images.githubusercontent.com/15976103/230866217-a20085a1-83e1-49f4-8827-9eeb11a06c7d.mov

Greenplum Q&A is a project that demonstrates how to use word embeddings and Postgres to build a chatbot. The chatbot is implemented using pgvector and relies on OpenAI's GPT-3.5 API to generate responses.

## Getting started

To get started with this project, you'll need to have:

- an API key for the OpenAI GPT-3.5 API, which you can obtain from https://openai.com/.

Once you have the prerequisites installed, follow these steps to get the project up and running:

Clone the repository:

```bash
git clone https://github.com/yihong0618/ask-greenplum.git
cd ask-greenplum
```

## Prepare the data


```console
docker run --name some-greenplum1 -e POSTGRES_PASSWORD=postgres -p 5432:5432  -d ankane/pgvector
```

```bash
cd data
python -m venv env
source env/bin/activate
pip install -r requirements.txt
```

Import the schema to your database:

```bash
psql <database-url> -f database.sql
```

Let’s now add `DATABASE_URL` and `OPENAI_API_KEY` to our environment variables:

```bash
export DATABASE_URL=<YOUR_PG_CONEECTION_STRING> 
OPENAI_API_KEY=<YOUR_OPENAI_API_KEY>
```



Run `main.py` to import the emebbeding to your pg database:

```bash
python main.py
```

Relax and grab a cup of coffee as this section might take 60mins to process!

Expcted result:

```bash
Saving to CSV...
Loading tokenizer...
Embedding text...
Connecting to database...
Done!
```


Set the following environment variables:

```
OPENAI_API_KEY= Your OpenAI API key.
DATABASE_URL= The connection URL for your docker postgres database.
```

## Ask

```console
pip install git+https://github.com/yihong0618/GPTerminator.git
```

## then

```console
gpterm # go ask
```

## Contributing

We welcome contributions to this project! If you find a bug, have a suggestion, or want to contribute code, please open an issue or pull request on the GitHub repository.

## License

This project is licensed under the MIT License. See the LICENSE file for more information.
