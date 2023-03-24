# Go Experiment

Simple REST web service written in go. Goal of the experiment is to deploy to AWS and write some tests that can be run in a CI/CD pipeline.

## Getting started

### Run the app

_Note: To run the app locally, you first need to [install go](https://go.dev/doc/install)._

If you have your local golang environment set up, you can continue here, alternatively, you can just skip this section and [run the app in a Docker container](#run-the-app-in-docker)

#### Fetch dependencies

```
go get .
```

#### Run the application

```
go run .
```

You should see an output similar to this:

```
[GIN-debug] GET    /albums                   --> main.getAlbums (3 handlers)
[GIN-debug] GET    /albums/:id               --> main.getAlbumById (3 handlers)
[GIN-debug] POST   /albums                   --> main.postAlbums (3 handlers)
...
[GIN-debug] Listening and serving HTTP on :8080
```

- To test the API, you can either execute the calls in `api.http` (e.g. by using the `REST Client` extension in VSCode) or just executing curl commands, e.g. `curl --request GET --url http://localhost:8080/albums`

### Run the app in Docker

#### Build the Docker Image

```
docker build -t go-experiment .
```

#### Run the docker image as a container

```
docker run --publish 8080:8080 go-experiment
```

### Run the tests

TODO

### Deploy to AWS

TODO

# Backlog

## 1st Iteration

- [x] Create simple REST endpoint in Go (based on https://go.dev/doc/tutorial/web-service-gin)
- [x] Run it in a container
- [ ] Deploy to AWS ECS

## 2nd Iteration

- [ ] Create unit test suite
- [ ] Create API test suite
- [ ] Run tests in CI/CD pipeline (environment TBD)
- [ ] deploy to AWS

## 3rd Iteration

- [ ] Add simple CRUD functionality
- [ ] Add a database
- [ ] Add tests for new functionality
- [ ] deploy to AWS
