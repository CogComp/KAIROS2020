## Requirements
1. python >= 3.6
2. pip install allennlp==0.8.5
3. pip install pytorch-pretrained-bert
4. pip install cherrypy
5. PyTorch 1.6.0 (install it after allennlp==0.8.5, as the latter enforces torch's early version=1.1.0)

## Instructions
Please run:
```
sh run.sh
```
Then please open another terminal and send the request. Examples of the request:
```
/**
 * If you only want to detect named entities (i.e. the tags are either 'NE' or 'O'),
 * then run this:
 */
curl -d '{"task": "mention_detection","text" : "Barack Hussein Obama, an American politician serving as the 44th President of the United States, graduated from Columbia University and Harvard Law School, where he served as president of the Harvard Law Review."}' -H "Content-Type: application/json" -X POST http://dickens.seas.upenn.edu:8099/ner/


/**
 * If you want to do named entities recognition on KAIROS (with 24 NE types and 'O'),
 * then you only need to change the "task":
 */
curl -d '{"task": "kairos_ner","text" : "Barack Hussein Obama, an American politician serving as the 44th President of the United States, graduated from Columbia University and Harvard Law School, where he served as president of the Harvard Law Review."}' -H "Content-Type: application/json" -X POST http://dickens.seas.upenn.edu:8099/ner


/**
 * If you want to do named entities recognition on other datasets or languages,
 * you might want to first update the model name in predict() of ner.py,
 * and then change the "task" in curl command:
 */
```
