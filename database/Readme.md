# Build the image
```
docker build -t <imagename> .
```
# Run the container
```
docker run -p 5432:5432 --name <container-name> <imagename>
```
# Access the psql console
```
docker exec -it database psql -U usr -d db
```
Verify that the tables were created
```
# \dt
```
# create volume
docker volume create postgres-volume
# create network
docker network create simple-net

# link with adminer
```
docker run --network=simple-net -p 5432:5432 -v postgres-volume:/var/lib/postgresql/data  --name database badido18/database

```