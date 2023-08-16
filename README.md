##image build and run
docker build . -t angulartest
docker images
docker run -d -p 8080:80 angulartest
docker ps

##volume
docker run --rm -d -p 5500:5500 -v $(pwd):/app --name angularTestContainer angularTest
docker ps
docker stop containerId

##environment
docker run --rm -d -p 5500:5600 -v $(pwd):/app -e PORT='5600' --name angularTestContainer angularTest
docker ps

##inside container
docker exec -it containerId bash
exit

##docker logs
docker logs containerId

##take whole file of .env
docker run --rm -d -p 5500:5600 -v $(pwd):/app --env-file ./.env --name angularTestContainer angularTest
