# DNA-RemoveDockerImages-None
Working with Docker Images from the command line

> You can list all the images you have downloaded or installed using the
```
docker images -a
```
> Sometimes when testing and developing, some images become dangling, which means untagged images. They can always be safely removed to free disk space.
```
docker images -f dangling=true
```
> And you can clear them with
```
docker rmi $(docker images -f dangling=true -q)
```
> Cek your Image :)

```docker system prune -a``` which is also a commonly used way to remove images, will also remove images not referenced by any container, which might remove images you might want to keep, even just to rollback to previous versions of an image.

You can also remove all images using ```docker rmi $(docker images -a -q)``` if you want to clean everything, which might be nice during your first tests and experiments with Docker.
