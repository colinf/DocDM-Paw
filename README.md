# DocDM-Paw
This is an experimental definition in [Paw][1] of the REST API for the new Document Data Model (DocDM) in Caché. For more information on DocDM see the Useful Links below.

![Paw screenshot][4]

## Environments
There are three environments defined in the Paw file which you can change, or copy and modify, to suit your requirements. The default values included in the file are shown in parentheses for each Paw environment variable.

### Server
		- Protocol (http)
		- Server (localhost)
		- Port (57772)
### Database
		- name (user)
### Collection
		- name (states)
		- sampleDoc (example JSON object containing definition of all states)

## APIs
The API examples included in the Paw file are listed below. In all cases the default values from the Server environment above are used in this README.

- [All collections for a database](#all-collections-for-a-database)
- [All documents for a collection](#all-documents-for-a-collection)
- [Get a document from a collection](#get-a-document-from-a-collection)
- [Get last inserted document from a collection](#get-last-inserted-document-from-a-collection)
- [Filtered documents for a collection](#filtered-documents-for-a-collection)
- [Populate a collection from Array](#populate-a-collection-from-array)
- [Delete a collection from the database](#delete-a-collection-from-the-database)
- [Insert new document in a collection](#insert-new-document-in-a-collection)
- [Update a document in a collection](#update-a-document-in-a-collection)
- [Update last inserted document in a collection](#update-last-inserted-document-in-a-collection)
- [Delete a document from a collection Duplicate](#delete-a-document-from-a-collection)
- [Delete last inserted document from a collection](#delete-last-inserted-document-from-a-collection)

#### All collections for a database
    GET http://localhost:57772/api/document/v1/{Database name}
#### All documents for a collection
    GET http://localhost:57772/api/document/v1/{Database name}/{Collection name}
#### Get a document from a collection
    GET /api/document/v1/{Database name}/{Collection name}/{Document Id}
You can use the _Document-Id_ header in the request as an easy way to enter the Document Id for your request (this is part of my Paw implementation, not the DocDM API).
#### Get last inserted document from a collection
This is the same as _Get a document from a collection_ except that the Document Id is automatically populated from the last document inserted.
#### Filtered documents for a collection
    POST http://localhost:57772/api/document/v1/{Database name}/{Collection name}?action=query
Returns all Documents from a Collection in a Database that match the Query specified in the body of the request.
#### Populate a collection from Array
    POST http://localhost:57772/api/document/v1/{Database name}/{Collection name}?action=insertArray
Populate a Collection by inserting one Document for each object in the array in the request body.
#### Delete a collection from the database
    DELETE http://localhost:57772/api/document/v1/{Database name}/{Collection name}
#### Insert new document in a collection
    POST http://localhost:57772/api/document/v1/{Database name}/{Collection name}
Insert a single Document into a Collection in a Database. The document to be inserted is defined as a JSON object in the request body.
#### Update a document in a collection
    PUT http://localhost:57772/api/document/v1/{Database name}/{Collection name}/{Document Id}
Update an existing Document within a Collection in a Database. The updated document defined as a JSON object in the request body. You can use the _Document-Id_ header in the request as an easy way to enter the Document Id for your request (this is part of my Paw implementation, not the DocDM API).
#### Update last inserted document in a collection
This is the same as _Update a document in a collection_ except that the Document Id is automatically populated from the last document inserted.
#### Delete a document from a collection
    DELETE http://localhost:57772/api/document/v1/{Database name}/{Collection name}/{Document Id}
Delete an existing Document from a Collection in a Database. You can use the _Document-Id_ header in the request as an easy way to enter the Document Id for your request (this is part of my Paw implementation, not the DocDM API).
#### Delete last inserted document from a collection
This is the same as _Delete a document from a collection_ except that the Document Id is automatically populated from the last document inserted.

## Useful Links
- [More information about DocDM][2]
- [The Swagger API that inspired this one][3]

[1]: https://luckymarmot.com/paw
[2]: https://beta.learning.intersystems.com/course/view.php?id=84
[3]: https://github.com/DannyWijnschenk/DocDMSwagger
[4]: http://cfshare.s3-eu-west-1.amazonaws.com/2016-05-31_13-15-30.png