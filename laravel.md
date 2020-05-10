# DOCUMENTACIÓ LARAVEL

## Comandes

### Servidor

- `php artisan serve`: Per activar un servidor (per defecte localhost:8000)

### Laravel

- `laravel new {nou_projecte}`: Et crea la carpeta i tota la suit d'arxius de laravel

#### Base de dades

- `php artisan make:model nouModel -m`: Per crear un model (es guarden a database\migrations\2020_05_06_171127_create_nouModels_table.php)
- `php artisan migrate`: Per posar al dia la base de dades en funció e tots els models 

#### Frontend

- `composer require laravel/ui`: Arrossega les dependències de Vue (probablement d'altres, també)
- `php artisan ui bootstrap`: per instal·lar bootstrap
- `php artisan ui vue --auth`: crea autenticació, amb les views (*resources\views\auth*)
- `npm run watch`: Et compila i cada cop que es fa un canvi, es recompila. D'aquesta manera veiem els canvis en temps real.

#### Backend

- `php artisan make:controller {Nom}Controller --resource`: crea el fitxer controlador en PHP (per poder comunicar amb la base de dades).

#### Altres

- `npm i`: S'ha d'executar després d'instal·lar qualsevol component del Frontend
- `npm run dev`: Ídem que l'anterior

## Tutorials

### Crear un projecte

1. Ens situem a la carpeta on es crearà el projecte (no cal crear la carpeta amb el nom) i executem `laravel new {nou_projecte}`
2. Si volem que el projecte utilitzi .vue, executem `composer require laravel/ui`. Si també volem que utilitzi authenticació, executem `php artisan ui vue --auth`.
3. Si volem que utilitzi bootstrap, executem `php artisan ui bootstrap`.
4. Un cop acabat executem `npm install` i després `npm run dev` per recompilar les instalacions.

### Inicialitzar una base de dades

1. Crea la base de dades a MySQL
2. Modifica l'arxiu `.env` de l'arrel:
    - `DB_CONNECTION=mysql`
    - `DB_HOST=127.0.0.1`
    - `DB_PORT=3306`
    - `DB_DATABASE={nom de la base de dades}`
    - `DB_USERNAME=root`
    - `DB_PASSWORD={password}`
3. Afegir a `app\Providers\AppServiceProvider.php` la següent llibreria:
    - `use Illuminate\Support\Facades\Schema;`
4. Crear el model (classe en PHP, t'ho crea a *app\Providers*) i la migració (detall de la taula, t'ho crea a *database\migrations*):
    - `php artisan make:model {Nom} -m` (el nom del model ha d'anar amb la primera amb majúscula).
5. Executem la migració (ens crea o modifica les taules):
    - `php artisan migrate`
6. Creem els controladors de la classe/taula {Nom} (ens crea el controlador a *app\Http\Controllers*):
    - `php artisan make:controller {Nom}Controller --resource`
7. Per automatitzar dades ficticies, haurem de crear un seed amb la comanda `php artisan make:seeder {NomSeeder}`. El nom pot ser `LibrosTableSeeder`
   1. Ens n'anem a `database\seeds\DatabaseSeeder.php` i modifiquem la següent línia comantada: `$this->call({NomSeeder}::class);`.
   2. Ens n'anem a `database\seeds\LibrosTableSeeder.php` i afegim codi a la funció `run()` per anar creant registres de proves:
        ```php
        Libro::truncate(); // Evita duplicar datos`
        $libro = new Libro();
        $libro->titulo = "Mi primer libro";
        $libro->descripcion = "Extracto de mi primer libro";
        $libro->contenido = "<p>Resumen de mi primer libro</p>";
        $libro->fecha = Carbon::now();
        $libro->categoria_id = 1;
        $libro->save();

        $libro->etiquetas()->attach([1, 2]); //Relacionar el libro a dos etiquetas`
        ```
    3. Per provar, podem refrescar totes les taules (s'eliminen i es tornen a crear) amb `php artisan migrate:refresh` i després executem `php artisan db:seed`.
    4. 

### Crear repository GIT

1. Per crear el repository: `git init`
2. Anem a [github](https://github.com/)
   1. Creem un repository amb el botó verd de dalt a l'esquerra `New`
   2. Posem un nom i una descripció, i escollim si volem que sigui Public o Privat.
3. Tornem al VS code i executem en aquest ordre:
   1. `git commit -m "first commit"` Per crear el primer commit
   2. `git remote add origin https://github.com/guillo1990/{nom_projecte}.git`
   3. `git push -u origin master`
4. A craftejar!






[Guia de Laravel bluuweb](https://bluuweb.github.io/tutorial-laravel/vue/#intalaciones)
