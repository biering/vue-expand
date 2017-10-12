<template>
  <div class="expanding-textarea">
    <textarea 
      ref="textarea"
      rows="1"
      :value="value"
      @input="$emit('input', $event.target.value); autoExpand()"
      :placeholder="placeholder"/>
  </div>
</template>

<script>
export default {
  name: 'expanding-textarea',

  props: {
    value       : { type: String, default: '' },
    placeholder : { type: String, default: '' },
    minRows     : { type: Number, default: 1 },
    handler     : { type: Object }
  },

  methods: {
    autoExpand () {
      const textarea = this.$refs.textarea

      textarea.rows = this.minRows
      // TODO: calculate value
      // 14 -> 17 optimal
      // 16 -> 24 optimal
      const rows = Math.ceil((textarea.scrollHeight - textarea.baseScrollHeight) / 24)
      textarea.rows = this.minRows + rows
    }
  },

  mounted () {
    this.handler.$on('focus', () => this.$refs.textarea.focus())

    const textarea = this.$refs.textarea
    const savedValue = textarea.value

    textarea.value = ''
    textarea.baseScrollHeight = textarea.scrollHeight
    textarea.value = savedValue
  }
}
</script>

<style scoped>
.expanding-textarea {
  display: flex;
}

textarea {
  outline: none;
  background: none;
  border: none;
  display: block;
  box-sizing: padding-box;
  overflow: hidden;
  resize: none;
  width: 100%;
}
</style>
