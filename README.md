# springboot-microservice-zuul
microservices with zuul gateway sample

Project has three microservices 
1) book
2) micro1
3) micro2

micro1 has the zuul configuration.

All the three microservices are running on different ports. Here using zuul configuration can consume the REST requests in other microservices as well.

Here, are the list of ports where microservices are running and sample endpoint
1) book -> 8090 -> http://localhost:8090/available
2) micro1 -> 8081 -> http://localhost:8081/testuri
3) micro2 -> 8082 -> http://localhost:8082/testuri

Use Zuul proxy configuration can consume the enpoints running on different microsevices in this case(book, micro2)
list of endpoints how to consume the same
1) http://localhost:8081/micro2/testuri
2) http://localhost:8081/book/available

In this sample because we set zuul.routes.micro2.url & zuul.routes.book.url, so Zuul will proxy requests /micro2 & /books to respective http://localhost:8082/ & http://localhost:8090/ hosts.

Note: Start book & micro2 application and then micro1
