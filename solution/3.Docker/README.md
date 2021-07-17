

### Test Docker
Log into node1 and test to make sure docker is working.

```
docker run hello-world
```

### Test docker-compose app
```
docker-compose up
```


## Troubleshooting
Sometimes if you made a mistake in one of the files, you made have to re-do the image build with docker-compose build
```
docker-compose build
```

# Testing
```
curl node1:5000
```
