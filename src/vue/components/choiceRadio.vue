<template>
  <div class="bmui-radio">
    <p class="bmui-radio-title">{{ title || 'TITLE' }}</p>
    <p class="bmui-radio-ctrls">
      <label
        class="bmui-radio-ctrl"
        v-for="item of items"
        :class="{ 'bmui-radio-disabled': item.disabled }">
        <input
          class="bmui-radio-input"
          v-bind="mixinInputProps"
          type="radio"
          :value="typeof item === 'string' ? item : item.value"
          v-model="valueInside"
          :disabled="item.disabled">{{ (typeof item === 'string' ? item : item.name) || 'ITEM' }}
      </label>
    </p>
  </div>
</template>
<script>
import MixinInput from 'src/vue/mixins/input'
export default {
  name: 'BmuiRadio',
  mixins: [MixinInput],
  props: {
    title: {
      type: String,
      default: ''
    },
    items: {
      type: Array,
      default: function () {
        return []
      }
    }
  }
}
</script>
