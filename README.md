# Custom Ruby Buildpack for Heroku

Questo buildpack personalizzato consente di usare versioni di Ruby non ufficialmente supportate da Heroku.

## Come usarlo

1. Aggiungi il buildpack alla tua applicazione Heroku:
   ```bash
   heroku buildpacks:add https://github.com/tuo-username/my-ruby-buildpack.git
   ```

2. Specifica la versione di Ruby nel tuo `Gemfile`:
   ```ruby
   ruby '2.6.10'
   ```

3. Effettua il deploy:
   ```bash
   git push heroku main
   ```

## Struttura del buildpack

- `bin/detect`: Riconosce se l'app usa Ruby.
- `bin/compile`: Scarica e installa la versione specificata di Ruby.
- `bin/release`: Definisce i processi di esecuzione per Heroku.

## Note

Assicurati che i tuoi file `Gemfile` e `Gemfile.lock` siano aggiornati.
