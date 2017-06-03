# vue-recyclerview

[![npm](https://img.shields.io/npm/v/vue-recyclerview.svg)](https://www.npmjs.com/package/vue-recyclerview)

Mastering Large Lists with the vue-recyclerview

## Preview

![](https://hilongjw.github.io/vue-recyclerview/preview2.gif)

## Demo

[https://hilongjw.github.io/vue-recyclerview/](https://hilongjw.github.io/vue-recyclerview/)

## Requirements

Vue 2.0 +

## Installation

### Direct Download / CDN

https://unpkg.com/vue-recyclerview/dist/vue-recyclerview

[unpkg.com](https://unpkg.com) provides NPM-based CDN links. The above link will always point to the latest release on NPM. You can also use a specific version/tag via URLs like https://unpkg.com/vue-recyclerview/dist/vue-recyclerview.js
 
Include vue-recyclerview after Vue and it will install itself automatically:

```html
<script src="https://unpkg.com/vue/dist/vue.js"></script>
<script src="https://unpkg.com/vue-recyclerview/dist/vue-recyclerview.js"></script>
```

### NPM

```bash
    $ npm install vue-recyclerview
```

When used with a module system, you must explicitly install the `vue-recyclerview` via `Vue.use()`:

```javascript
import Vue from 'vue'
import VueRecyclerviewNew from 'vue-recyclerview'

Vue.use(VueRecyclerviewNew)
```

You don't need to do this when using global script tags.

### Dev Build

You will have to clone directly from GitHub and build `vue-recyclerview` yourself if
you want to use the latest dev build.

    $ git clone git@github.com:hilongjw/vue-recyclerview.git node_modules/vue-recyclerview
    $ cd node_modules/vue-recyclerview
    $ npm install
    $ npm run build


## Getting Started

> We will be using [ES2015](https://github.com/lukehoban/es6features) in the code samples in the guide.

### main.js

```javascript
// If using a module system (e.g. via vue-cli), import Vue and RecyclerView and then call Vue.use(RecyclerView).
// import Vue from 'vue'
// import RecyclerView from 'vue-recyclerview'
// import App from './App.vue'
// Vue.use(RecyclerView)

// Now the app has started!
new Vue({
  render: h => h(App)
}).$mount('#app')
```

### App.vue

```html
<template>
  <div id="app">
    <RecyclerView
      :prerender="30"
      style="height: calc(100vh - 50px)"
      :fetch="MiFetch" 
      :item="MiItem" 
      :tombstone="MiTomstone"
    ></RecyclerView>
  </div>
</template>

<script>
import MiItem from './MiItem.vue'
import MiTomstone from './MiTombstone.vue'
import MiFetch from './mi-fetch'

export default {
  name: 'app',
  data () {
    return {
      MiFetch,
      MiItem,
      MiTomstone
    }
  }
}
</script>
```

[Full example code](https://github.com/hilongjw/vue-recyclerview/blob/master/examples/component)

## Props Options

### fetch:Function

@params limit Number
@params skip Number

return Promise { count: Number, list: Array }

### list:Array

RecyclerView list data

```javascript
[
// item
{
  vm: vm, // <Vue Instance>
  data: {
    name: 'test'
  },
  node: null,
  height: 100,
  width: 100,
  top: 0,
}, 
// tombstone
{
  vm: null
  data: null,
  node: null,
  height: 100,
  width: 100,
  top: 0,
}]
```

### prerender:Number

Number of items to instantiate beyond current view in the opposite direction.


### remain:Number

Number of items to instantiate beyond current view in the opposite direction.


### item:Vue Component


### tombstone:Vue Component


### loading:Vue Component


## Instance Method

### scrollToIndex

```javascript
const index = 100
this.$refs.RecyclerView.scrollToIndex(index)

```

## License

[MIT](https://github.com/hilongjw/vue-recyclerview/blob/master/License)

the project inspired by [infinite-scroller](https://github.com/GoogleChrome/ui-element-samples/tree/gh-pages/infinite-scroller)


