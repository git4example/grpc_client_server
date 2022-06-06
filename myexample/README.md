

Build Server : 
```
docker build -t grpc_server -f Dockerfile_server .
```

Run Server:

```
docker run -d -p 50051:50051 grpc_server
```

Build Client : 
```
docker build -t grpc_client -f Dockerfile_client .
```
Running on host network mode so that client can talk to server on localhost:50051 else set 
```
docker run -it --net=host -e SRVNAME=<your-client-service-name> grpc_client

docker run -it -e SRVNAME=<your-client-service-name> -e SERVER_HOST=<server-ip/endpont> grpc_client
```

Output : Will be `Hello <Service-name>:<randomnumber>`

```
2022/06/06 03:08:54 Greeting: Hello test-service:16807
2022/06/06 03:08:57 Greeting: Hello test-service:15089
```