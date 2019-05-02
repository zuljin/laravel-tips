### intersect()
Supongamos que tenemos dos colecciones de usuarios, una llamada $usersA y otra $usersB. En $usersA tenemos una colección de usuarios obtenidos por cierta condición y queremos saber si los usuarios de $usersB existen en $usersA, entonces haríamos:

```
$usersA = User:where('status', 'approved')
              ->whereHas('product', function ($query {
                $query->where('price', '>', 100);
               })->get();
$results = $users->intersect($usersB);
```

En este ejemplo, $results contendrá todos los usuarios de B que cumplan con la condición que fue dada para obtener los usuarios del grupo A.
