#stage-1

FROM python:3.8-slim AS build

WORKDIR /app/

COPY requirements.txt /app/

RUN pip install --target=/app/requirements -r requirements.txt


# #stage-2
FROM python:3.8-slim

WORKDIR /app/

COPY --from=build /app/requirements /app/



EXPOSE 5000

# FROM sainathvelaga/bestpractices:1.0

RUN echo $PATH

RUN python -c "import nltk; nltk.download('omw-1.4'); nltk.download('wordnet')"



CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]