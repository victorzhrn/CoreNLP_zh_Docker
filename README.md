# CoreNLP_zh-Docker
CoreNLP server with Chinese support as Docker Image. Please note, only Chinese as pipelineLanguage is supported in this docker image.

## Usage
#### Pull docker image from DockerHUB
```bash
docker pull zhangruinan/corenlp_zh
```
#### Run CoreNLP_zh Server as a docker container
```bash
docker run -i -p 9000:9000 corenlp_zh
```
#### Analyze a document
```bash
wget --post-data '今天天气不错' 'localhost:9000/?properties={"annotators": "tokenize,sentiment", "outputFormat": "json","pipelineLanguage":"zh"}' -O -
```
Output:
```Javascript
"sentences": [
   {
     "index": 0,
     "parse": "(ROOT\n  (IP\n    (NP (NT 今天))\n    (NP (NN 天气))\n    (VP (VA 不错))))",
     "basicDependencies": [
       {
         "dep": "ROOT",
         "governor": 0,
         "governorGloss": "ROOT",
         "dependent": 3,
         "dependentGloss": "不错"
       },
       {
         "dep": "nmod:tmod",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 1,
         "dependentGloss": "今天"
       },
       {
         "dep": "nsubj",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 2,
         "dependentGloss": "天气"
       }
     ],
     "enhancedDependencies": [
       {
         "dep": "ROOT",
         "governor": 0,
         "governorGloss": "ROOT",
         "dependent": 3,
         "dependentGloss": "不错"
       },
       {
         "dep": "nmod:tmod",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 1,
         "dependentGloss": "今天"
       },
       {
         "dep": "nsubj",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 2,
         "dependentGloss": "天气"
       }
     ],
     "enhancedPlusPlusDependencies": [
       {
         "dep": "ROOT",
         "governor": 0,
         "governorGloss": "ROOT",
         "dependent": 3,
         "dependentGloss": "不错"
       },
       {
         "dep": "nmod:tmod",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 1,
         "dependentGloss": "今天"
       },
       {
         "dep": "nsubj",
         "governor": 3,
         "governorGloss": "不错",
         "dependent": 2,
         "dependentGloss": "天气"
       }
     ],
     "sentimentValue": "3",
     "sentiment": "Positive",
     "sentimentDistribution": [
       0.02866044340565,
       0.12261030093566,
       0.13119351817913,
       0.49430368213791,
       0.22316515079736,
       0.00006690454429
     ],
     "sentimentTree": "(ROOT|sentiment=3|prob=0.494 (NP|sentiment=3|prob=0.327 今天)\n  (@IP|sentiment=3|prob=0.474 (NP|sentiment=2|prob=0.705 天气) (VP|sentiment=3|prob=0.486 不错)))",
     "entitymentions": [
       {
         "docTokenBegin": 0,
         "docTokenEnd": 1,
         "tokenBegin": 0,
         "tokenEnd": 1,
         "text": "今天",
         "characterOffsetBegin": 0,
         "characterOffsetEnd": 2,
         "ner": "DATE",
         "normalizedNER": "XXXX-XX-XX"
       }
     ],
     "tokens": [
       {
         "index": 1,
         "word": "今天",
         "originalText": "今天",
         "lemma": "今天",
         "characterOffsetBegin": 0,
         "characterOffsetEnd": 2,
         "pos": "NT",
         "ner": "DATE",
         "normalizedNER": "XXXX-XX-XX"
       },
       {
         "index": 2,
         "word": "天气",
         "originalText": "天气",
         "lemma": "天气",
         "characterOffsetBegin": 2,
         "characterOffsetEnd": 4,
         "pos": "NN",
         "ner": "O"
       },
       {
         "index": 3,
         "word": "不错",
         "originalText": "不错",
         "lemma": "不错",
         "characterOffsetBegin": 4,
         "characterOffsetEnd": 6,
         "pos": "VA",
         "ner": "O"
       }
     ]
   }
 ]
}

```
