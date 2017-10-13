# vue-expand

> Light-weight auto expanding textarea as a vue component

## Install

```bash
npm install --save vue-expand

# or

yarn add vue-expand
```

## Usage

Add this to your vue-component:

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
|`v-model`|`String`|The value which is bound to the text area|
|`min-row`|`Number`|Minimum number of rows which results in the initial text area height|
|`placeholder`|`String`|The placeholder of the text area|
|`handler`|`Function`|Handler to access vue-expand through events|

### Handler Events

You can use the handler in the following way:

```javascript
this.handler.$emit(event, [args])

// for example
this.handler.$emit('focus')
```

|Name|Arguments|Description|
|:--:|:--:|:--|
|`focus`||Focus the textarea|

### Styling

To style the textarea add this class somewhere in a **non-scoped** style-block:

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
