#stage-1

FROM python:3.8-slim as build

COPY requirements.txt /app/

RUN pip install --no-cache-dir --target=/app/requirements -r requirements.txt


#stage-2
FROM python:3.8-slim

COPY --from=build /app/requirements/ /app/

RUN python -c "import nltk; nltk.download('omw-1.4'); nltk.download('wordnet')"



EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]