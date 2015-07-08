# langid

Dockerfile for language identification, based on langid.py. Returns the text's indentified language with confidence score in JSON.
    
    
To start the server:   
```
docker run mbartoli/langid python langid.py -s
```
    
To classify a string of text:     
```
curl -d "Io non parlo italiano" [SERVER_IP_ADDRESS_GOES_HERE]:9008/detect
```
   
To classify a text file:   
```
curl -T [FILE_LOCATION_GOES_HERE] [SERVER_IP_ADDRESS_GOES_HERE]:9008/detect
```
   

See https://github.com/saffsd/langid.py for additional implementation details.
