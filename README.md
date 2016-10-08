docker run -it -p 3000:3000 image-microservice go run 3000/main.go
docker run -it -p 3001:3001 image-microservice go run 3001/task.go '192.168.3.12:3001' '192.168.3.12:3000'
docker run -it -p 3002:3002 image-microservice go run 3002/storage.go '192.168.3.12:3002' '192.168.3.12:3000'
docker run -it -p 3003:3003 image-microservice go run 3003/master.go '192.168.3.12:3003' '192.168.3.12:3000'
docker run -it -p 8080:80 image-microservice go run frontend.go '192.168.3.12:3000' ''
