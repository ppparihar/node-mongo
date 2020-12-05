docker run --name mongodb -p 27017:27017 -d  mongo

#Create a docker network
docker network create my-net

docker run --name mongodb --network my-net -d  mongo

docker build -t pparihar/node-mongo-app .
docker run --name node-mongo-app --network my-net -p 8080:8080 --env mongodb=mongodb -d  pparihar/node-mongo-app