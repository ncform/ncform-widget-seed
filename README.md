# nc-demo

nc-demo widget for [ncform](https://github.com/ncform/ncform)

## Install and basic usage

```
npm i -s nc-demo
```

**Add the widget**

```
import ncDemo from 'nc-demo';

Vue.use(vueNcform, { extComponents: {ncDemo} });

// or vm.$ncformAddWidget({name: 'ncDemo', widget: ncDemo});

```

**Use the widget**

```
{
  "type": "object",
  "properties": {
    "name": {
      "type": "string",
      "widget": "nc-demo",
      "widgetConfig": {
      }
    }
  }
}
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

You only need to care about `src/components/index.vue`

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Run your end-to-end tests
```
npm run test:e2e
```

### Run your unit tests
```
npm run test:unit
```
