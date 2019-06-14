# Adding Sass to Node/Express

- `npm i node-sass-middleware --save`
- do the following setup in your server file.
- make sure the app.use Sass middleware is above the app.use for the static public.

```js
const sassMiddleware = require('node-sass-middleware');

app.use(
  sassMiddleware({
    src: 'scss',
    dest: 'public/styles',
    debug: true,
    outputStyle: 'compressed',
    prefix: '/styles', // Where prefix is at <link rel="stylesheets" href="prefix/style.css"/>
    // exemple:
    //  in index.html: <link rel="stylesheet" href="/styles/main.css">
  })
);

app.use(express.static('public'));

app.listen(PORT, () => {
  console.log('Example app listening on port ' + PORT);
});
```
