cd $WORKSPACE
mvn site
docker build -t captest .
docker save captest > captest.tar ; docker rm $(docker ps -aq); docker rmi $(docker images -aq); docker load -i captest.tar; docker images
