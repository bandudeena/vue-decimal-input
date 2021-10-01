<template>
  <div>
      <div>
      <input
          type='number'
          :value="formatWithDecimals()"
          :id="id"
          :class="classes"
          :placeholder="placeholder"
          :disabled="disabled"
          :name="name"
          :step="step"
          @change="handleInput"
          :required="required"
      />
      </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'VueDecimalInput',
  emits: ['update:modelValue'],
  props: {
    id: {
      type: String,
      required: false
    },
    modelValue: {
      type: [Number],
      required: false,
      default: null
    },
    required: {
      type: Boolean,
      required: false,
      default: false
    },
    placeholder: {
      type: String,
      required: false,
      default: null
    },
    disabled: {
      type: Boolean,
      required: false,
      default: false
    },
    name: {
      type: String,
      required: false,
      default: null
    },
    step: {
      type: Number,
      required: false,
      default: 5
    },
    classes: {
      type: Object,
      required: false,
      default: null
    },
    decimal: {
      type: Number,
      required: false,
      default: 2
    }
  },
  methods: {
    handleInput: function (e) {
      this.$emit(
        'update:modelValue',
        e.target.value === '' ? null : e.target.value
      );
    },
    formatWithDecimals() {
      if (this.modelValue) {
        return this.modelValue.toFixed(this.decimal);
      } 
      return this.modelValue;
    }
  }
});
</script>

