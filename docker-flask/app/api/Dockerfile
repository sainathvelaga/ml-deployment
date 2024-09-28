#stage-1

FROM python:3-alpine3.8 

WORKDIR /app

COPY . /app

RUN pip install -r requirements.txt




RUN python -c "import nltk; nltk.download('omw-1.4'); nltk.download('wordnet')"



CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]