# vue-expand

> Light-weight auto expanding textarea as a vue component

## Install

```bash
npm install --save vue-expand
```

## Usage

In your vue component:

```vue
<template>
  <div>
    <vue-expand
      v-model="text" 
      :placeholder="A placeholder" 
      :handler="handler" 
      min-row="3"/>
  </div>
</template>

<script>
import VueExpand from 'vue-expand'

export default {
  name: '..',

  components: {
    VueExpand
  },

  data () {
    return {
      text: '',
      handler: new Vue()
    }
  },
  ...
}
</script>
```

### Options

|Property|Type|Description|
|:--:|:--:|:--|
|`v-model`|`String`|The value bind to the textarea|
|`min-row`|`Number`|Minimum number of rows which determine the initial textarea height|
|`placeholder`|`String`|The placeholder of the textarea|
|`handler`|`Function`|Access event on the textarea|

### Handler Events

Use the handler as following:

```javascript
this.handler.$emit(event, [callback])
```

|Name|Description|
|:--:|:--|
|`focus`|Focus the textarea|

### Styling

To style the textarea add this class somewhere in a non-scoped style-block:

```vue
<style>
  /* wrapper element */
  .vue-expand {
    ...
  }

  /* wrapper textarea */
  .vue-expand textarea {
    ...
  }
</style>
```

## License

Copyright (c) 2017 Christoph Biering, Licensed under the [MIT license](./LICENSE).
