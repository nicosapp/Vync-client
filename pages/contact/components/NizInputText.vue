<template>
  <div class="mb-4">
    <label
      >{{ label }}
      <span v-if="required" class="required text-gray-500">* </span>
    </label>
    <input
      v-if="!textarea"
      class="outline-none border-0 bg-gray-200 w-full py-2 px-2 rounded"
      type="text"
      name="firstname"
    />
    <textarea
      v-else
      rows="6"
      class="outline-none border-0 bg-gray-200 w-full py-2 px-2 rounded"
    ></textarea>
  </div>
</template>
<script>
export default {
  props: {
    label: {
      required: false,
      type: String,
      default: '',
    },
    required: {
      required: false,
      type: Boolean,
      default: false,
    },
    textarea: {
      required: false,
      type: Boolean,
      default: false,
    },
  },
}
</script>
