## Create model and migration

### To generate the factory, enter the following command mentioning the reference model.

``` bash
$ php artisan make: factory Namefactory --model = Models \ Namereferencemodel
```

#### Having populated the factory, go to the reference seeder, mention the factory, model and the number of records.

```
factory (Namereferencemodel :: class, quantityTypeInt) -> create ();
```

#### Having followed the steps above, enter the command to generate the fakes data in the database table.
