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
    <expanding-textarea
      v-model="text" 
      :placeholder="A placeholder" 
      :handler="handler" 
      min-row="3"/>
  </div>
</template>

<script>
import ExpandingTextarea from 'vue-expand'

export default {
  name: '..',

  components: {
    ExpandingTextarea
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


## License

Copyright (c) 2017 Christoph Biering, Licensed under the [MIT license](./LICENSE).
