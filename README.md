docker build . -t angulartest
docker images
docker run -p 8080:80 angulartest