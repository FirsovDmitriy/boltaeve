<template>
  <input :value="modelValue" @input="updateInput" type="text" class="control" />
</template>

<script>
export default {
  name: "BaseControl",

  props: {
    modelValue: {
      type: [String, Number],
    },
  },

  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style lang="scss" scoped>
.control {
  width: 100%;
  padding: 24px 0 24px 0;
  background-color: transparent;
  border-bottom: 1px solid rgba(85, 85, 85, 0.2);
}

.control,
.control::placeholder {
  font-size: 20px;
}

.control::placeholder {
  line-height: 1.1;
  color: #555555;
  opacity: 0.5;
}

input::-webkit-input-placeholder {
  transition: opacity 0.2s ease;
}

input::-moz-placeholder {
  transition: opacity 0.2s ease;
}

input:-moz-placeholder {
  transition: opacity 0.2s ease;
}

input:-ms-input-placeholder {
  transition: opacity 0.2s ease;
}

input:focus::-webkit-input-placeholder {
  opacity: 0;
}

input:focus::-moz-placeholder {
  opacity: 0;
}

input:focus:-moz-placeholder {
  opacity: 0;
}

input:focus:-ms-input-placeholder {
  opacity: 0;
}
</style>
