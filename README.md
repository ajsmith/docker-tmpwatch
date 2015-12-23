# docker-tmpwatch

Docker image which runs tmpwatch. This is useful for removing old files from a
filesystem.

This image is based on the official Fedora 23 image.

# Building

To build the image, run:

```.shell
$ docker build -t tmpwatch .
```

# Running

This image declares an entrypoint to the `tmpwatch` executable. Simply add
options when running the container.

To get help on using using the tmpwatch command, simply run it with no
arguments:

```.shell
$ docker run --rm ajsmith/tmpwatch
```

To remove files more than 7 days old from a container volume, run:

```.shell
$ docker run --rm --volumes-from=my-container ajsmith/tmpwatch 7d /path/to/volume
```

In the example above, replace `my-container` with the appropriate container
identifier.
