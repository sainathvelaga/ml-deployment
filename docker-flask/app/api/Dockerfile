#stage-1

FROM python:3-alpine3.8 AS build

WORKDIR /app

COPY . /app

RUN pip install -r requirements.txt


# #stage-2
FROM python:3-alpine3.8

WORKDIR /app

COPY --from=build /app/ .



EXPOSE 5000

# FROM sainathvelaga/bestpractices:1.0

RUN echo $PATH

RUN python -c "import nltk; nltk.download('omw-1.4'); nltk.download('wordnet')"



CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]