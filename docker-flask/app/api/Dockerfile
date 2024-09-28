#stage-1

FROM python:3.8-slim AS build

WORKDIR /app/

COPY requirements.txt /app/

RUN pip install -r requirements.txt


# #stage-2
# FROM python:3.8-slim

# COPY --from=build /app/ /app/

FROM sainathvelaga/bestpractices:1.0

RUN python -c "import nltk; nltk.download('omw-1.4'); nltk.download('wordnet')"



EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]