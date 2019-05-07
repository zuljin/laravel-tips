### intersect()  >= Laravel 4.2
Supongamos que tenemos dos colecciones de usuarios, una llamada $usersA y otra $usersB. En $usersA tenemos una colección de usuarios obtenidos por cierta condición y queremos saber si los usuarios de $usersB existen en $usersA, entonces haríamos:

```
$usersA = User:where('status', 'approved')
              ->whereHas('product', function ($query {
                $query->where('price', '>', 100);
               })->get();
$results = $users->intersect($usersB);
```

En este ejemplo, $results contendrá todos los usuarios de B que cumplan con la condición que fue dada para obtener los usuarios del grupo A.

### load()

Carga relaciones al vuelo en modelos optimizando así las consultas.

```
class User extends Model
{
  // relation
  public function products() 
  {
    return $this->hasMany(Product:class);
  }
}
// load method-relation name. For each user we will have "products".
$user->load('products');
```
