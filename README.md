# vite-bootstrap

Quick example of using [vite](https://vitejs.dev/) with reactstrap and custom boostrap variables.

Live version deployed [here](https://vite-bootstrap.surge.sh/).

## usage

```sh
npm i          # install tools
npm start      # run local dev-server
npm run build  # build static site in dist/
npm run deploy # deploy static site on surge
npm run lint   # clean up code to follow standardjs
```



## process

This is what I did to turn default into custom bootstrap site:

I made the initial project, like [this](https://asciinema.org/a/obRS03giA1To87sM6ufHy7g6L).

```sh
npm init @vitejs/app vite-bootstrap
cd vite-bootstrap
```

```sh
# add tools & libs
npm i -D sass surge standard
npm i reactstrap bootstrap

# get rid of default App.css and use my bootstrap override
rm src/App.css
sed 's/@import "/@import "bootstrap\/scss\//g' node_modules/bootstrap/scss/bootstrap.scss > src/App.scss

# locally override variables
cp node_modules/bootstrap/scss/_variables.scss src/variables.scss

# go edit App.jsx to use App.scss instead of App.css
# edit App.scss to use `./variables` instead of `bootstrap/scss/variables`
```

After this, you can override any bootstrap scss locally (like I did with `variables`) or just comment it out, if you don't need it.