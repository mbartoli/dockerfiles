# docker-ner
Docker container for Stanford Named Entity Recognizer (NER)

Start the NER server
```
java -mx1000m -cp stanford-ner.jar edu.stanford.nlp.ie.NERServer \     
     -loadClassifier classifiers/english.muc.7class.distsim.crf.ser.gz  \
     -port 8080 -outputFormat inlineXML & 
```

Example from inside of iPython
```
import ner
tagger = ner.SocketNER(host='localhost', port=8080)
tagger.get_entities("Pomona College is located in California, United States")
```
