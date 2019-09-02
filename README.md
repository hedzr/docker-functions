# docker-functions

A collections of docker function shortcuts.



## Import and Use It

in your `$HOME/.bashrc` or `$HOME/.zshrc`, source it:

```bash
source /some/path/to/docker-functions
```

### Use one-line helper

The one-line script could make everything done to use me:

```bash
TGT=/opt wget https://github.com/hedzr/docker-functions/raw/master/docker-functions -O $TGT/docker-functions && echo ". $TGT/docker-functions" >>$HOME/.bashrc
```



## Documentations

These shortcuts are available In `docker-functions`:

### `docker-cid`

To retrieve the container id.

```bash
$ docker run -d mysql
$ docker-cid mysql
91cec59f0a97
$ docker stop mysql; docker rm -f mysql
```



### `docker-pid`

To retrieve the process id of a container.

```bash
$ docker-pid $(docker-cid mysql)
3193
```



### `docker-stop-all`

To stop all running containers in one command.

```bash
docker-stop-all
```



### `docker-kill-all`

= `docker-rm-all -f`



### `docker-rm-all`

To remove all stopped containers, or remove all running containers anyway (`-f`)

```bash
docker-rm-all     # remove all stopped containers
docker-rm-all -f  # remove all containers even if its are running.
```



### `docker-rmi`

To remove an image.

```bash
docker-rmi mysql:8
```



### `docker-rmi-none`

To remove all containers without name (identified as `<none>`)

```bash
docker-rmi-none
```



### `docker-images-none`

To list any containers without name

```bash
docker-images-none
```



### `docker-is-running`

To detect if a container is running or not.

```bash
docker-is-running mysql:8 && echo "running" || echo "not running"
```



### `docker-is-exists`

To detect if a container or an image is exists or not.

```bash
docker-is-exists mysql:55 && echo 'exists' || docker pull mysql:55
docker-is-exists mysql:8 || docker pull mysql:8
```



## LICENSE

MIT











