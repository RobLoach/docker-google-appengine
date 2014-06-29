# Docker: Google App Engine

[Google App Engine](https://developers.google.com/appengine/) [Docker](http://docker.com) container, through [Docker Forge](http://github.com/robloach/forge).

http://github.com/robloach/docker-google-appengine


## The Idea

Easily set up and run Google App Engine web applications through Docker, without
needing to install the Google App Engine SDK, or set up the development
environment locally. Support for Go, PHP, Java, or any other Google App Engine
SDK runtime available.


## Features

* [Forge](../forge)
* [Google App Engine SDK](https://developers.google.com/appengine) 1.9.6


## Usage

### Install

Pull `robloach/docker-google-appengine` from the Docker repository:
```
docker pull robloach/docker-google-appengine
```

Or build robloach/docker-google-appengine` from source:
```
git clone https://github.com/RobLoach/docker-google-appengine.git
docker build -t robloach/docker-google-appengine robloach/docker-google-appengine
```

### Run

Run the image, binding associated ports, and mounting the
application directory:

```
docker run -v $(pwd)/test/php:/app -p 8080:8080 -p 8000:8000 -p 222:22 robloach/docker-google-appengine
```


## Services

Service      | Port | Usage
-------------|------|------
SSH          | 22   | Connect with `ssh root@localhost -p 422` with the password `root`
Application  | 8080 | Visit `http://localhost:8080` in your browser
Admin server | 8000 | Visit `http://localhost:8000` in your browser


## Volumes

Volume          | Description
----------------|-------------
`/app`          | The location of your Google App Engine application
