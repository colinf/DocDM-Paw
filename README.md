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

- [All collections for a database](#All collections for a database)
- [All documents for a collection](#All documents for a collection)

#### All collections for a database
    GET http://localhost:57772/api/document/v1/{Database name}
#### All documents for a collection
    GET http://localhost:57772/api/document/v1/{Database name}/{Collection name}

## Useful Links
- [More information about DocDM][2]
- [The Swagger API that inspired this one][3]

[1]: https://luckymarmot.com/paw
[2]: https://beta.learning.intersystems.com/course/view.php?id=84
[3]: https://github.com/DannyWijnschenk/DocDMSwagger
[4]: http://cfshare.s3-eu-west-1.amazonaws.com/2016-05-31_13-15-30.png