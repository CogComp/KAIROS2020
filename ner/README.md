## Requirements
1. python >= 3.6
2. PyTorch 1.6.0
3. pip install allennlp==0.8.5
4. pip install pytorch-pretrained-bert
5. pip install cherrypy

## Instructions
Please run:
```
sh run.sh
```
Then please open another terminal and send the request. One example of the request:
```
curl -d '{"task": "mention_detection","text" : "Barack Hussein Obama, an American politician serving as the 44th President of the United States, graduated from Columbia University and Harvard Law School, where he served as president of the Harvard Law Review."}' -H "Content-Type: application/json" -X POST http://dickens.seas.upenn.edu:8099/ner/
```
