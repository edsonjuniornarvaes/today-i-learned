# Change the repository source.

##### Within the project, follow the steps below.

##### First check the source of your repository.

``` bash
git remote -v
```

##### Rename the current source to ensure that there will be no conflict.

``` bash
git remote rename originname ancient-origin
```

##### Define the new repository source.

``` bash
git remote add origin repository_address
```

##### Check if the changes occurred as requested.

``` bash
git remote -v
```

###### To avoid the accumulation of sources, remove the old source.

``` bash
git remote rm ancient-origin
```

### Again, check that the changes have occurred as requested.

``` bash
git remote -v
```
