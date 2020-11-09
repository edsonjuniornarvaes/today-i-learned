## Environment Resources

### Removing all resources

##### Docker offers a command to remove unused containers, networks and images.

#### To remove:
- All containers stopped
- All networks not used by at least one container
- All pending images (dangling images)
- All pending cache build

```bash
$ docker system prune
```

#### To remove:
- All containers stopped
- All networks not used by at least one container
- All volumes not used by at least one container
- All images without any associated containers
- All cache build pending

```bash
$ docker system prune --all --force --volumes
```

Reference:

- http://www.macoratti.net/19/02/dock_limp1.htm
