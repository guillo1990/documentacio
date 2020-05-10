# DOCUMENTACIÓ GIT

## Comandes

### Crear repository a GITHUB

1. Per crear el repository: `git init`
2. Anem a [github](https://github.com/)
   1. Creem un repository amb el botó verd de dalt a l'esquerra `New`
   2. Posem un nom i una descripció, i escollim si volem que sigui Public o Privat.
3. Tornem al VS code i executem en aquest ordre:
   1. `git commit -m "first commit"` Per crear el primer commit
   2. `git remote add origin https://github.com/guillo1990/{nom_projecte}.git`
   3. `git push -u origin master`
4. A craftejar!

### Crear versió de l'aplicació (new TAG)

1. Per crear una nova versió s'ha de llançar la següent comanda a la carpeta del projecte `git tag {nom_versió} -m "{descripció_versió}"`
2. En aquest cas, no s'ha de fer commit ni res. Només s'ha de fer push, però s'ha d'afegir el següent paràmetre: `git push --tags`
3. Gràcies a això, s'haurà creat una nova Release que es pot baixar directament des de la web de [github](https://github.com/)




[Guia de Laravel bluuweb](https://bluuweb.github.io/tutorial-github/guia/)