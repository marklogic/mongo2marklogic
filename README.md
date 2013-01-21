MongoImport README
http://www.marklogic.com

MongoImport is a POC for support for importing data from a Mongo Database into a MarkLogic dataase.
BUILD

    ant jar

Result
   mongoimport.jar
   
   
RUN


To import a collection generated from mongodump and store to a MarkLogic server run  
   java -jar mongoimport.jar  [-input file] -connection conn [-root root] [-collection collection] [-threads n] [-batch n] [-writer json|bson]
   
To import a collection generated from mongodump and store to a local filesystem directory as XML documents
    java -jar mongoimport.jar [-input file] -directory dir [-writer json|bson]
   
Options
   -input filename   
          Specifies the input bson file
          Default: reads from stdin
   -threads n
          Specifies the number of threads to use for writing to the MarkLogic server
          Default: 1
   -batch  n
          Specifies the number of documents to batch in a single transaction
          Default: 100
   -root uri
          Specifies the root URI to place generated XML files in MarkLogic
          Default: "" 
          
   -collection coll
           Specifies the collection to place the documents
           Default: none
          
   -connection  url
          Specifies the xcc or xccs connection 
          Default: xcc://localhost:9003
   
   -directory dir
          Specifies that files are to be written to a local filesystem directory "dir" instead of storing in a MarkLogic server
    
   -writer  json|bson
          Indicates which format is used for XML document generation.  "json" indicateds to use the MarkLogic XML JSON format.  
          "bson" indicates to use a fully semanticaly rich XML format designed for storing mongo data.
          
          
          
   
   
Documents are created named 

      <root><random #>.xml
      
