#### When use GET() When POST() 
* **GET** is used to request something from server with less amount of data to pass. 
* When nothing should change on the server because of your action. 
* When request only retrieves data from a web server by specifying parameters 
* Get method only carries request `url` & header not request body. 

* **POST** should be used when the server state changes due to that action.
* When request needs its body, to pass large amount of data. 
* When want to upload documents , images , video from client to server

##### The following table compares the two HTTP methods: GET and POST.

| Key Points                  | GET                                                                                                                                                      | POST                                                                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| BACK button/Reload          | Harmless                                                                                                                                                 | Data will be re-submitted (the browser should alert the user that the data are about to be re-submitted)       |
| Bookmarked                  | Can be bookmarked                                                                                                                                        | Cannot be bookmarked                                                                                           |
| Cached                      | Can be cached                                                                                                                                            | Not cached                                                                                                     |
| Encoding type               | application/x-www-form-urlencoded                                                                                                                        | application/x-www-form-urlencoded or multipart/form-data. Use multipart encoding for binary data               |
| History                     | Parameters remain in browser history                                                                                                                     | Parameters are not saved in browser history                                                                    |
| Restrictions on data length | Yes, when sending data, the GET method adds the data to the URL; and the length of a URL is limited (maximum URL length is 2048 characters)              | No restrictions                                                                                                |
| Visibility                  | Data is visible to everyone in the URL                                                                                                                   | Data is not displayed in the URL                                                                               |
| Restrictions on data type   | Only ASCII characters allowed                                                                                                                            | No restrictions. Binary data is also allowed                                                                   |
| Security                    | GET is less secure compared to POST because data sent is part of the URL  <br>  <br>Never use GET when sending passwords or other sensitive information! | POST is a little safer than GET because the parameters are not stored in browser history or in web server logs |
