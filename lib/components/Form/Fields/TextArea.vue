<template>
  <div v-form-field="field" class="whppt-form-textarea">
    <field-label :field="field" :show-error="showError"></field-label>
    <textarea
      v-model="value"
      v-whppt-text="field"
      data-property="placeholder"
      :placeholder="field.placeholder"
      rows="5"
      @input="$emit('field-updated', { name: field.name, value })"
    />
  </div>
</template>

<script>
import FieldLabel from './FieldLabel';

export default {
  name: 'FormTextArea',
  components: { FieldLabel },
  props: { field: { type: Object, default: () => ({}) }, showError: { type: Boolean, default: false } },
  data: () => ({
    value: '',
  }),
};
</script>

<style>
.whppt-form-textarea {
  margin-bottom: 2rem;
}

.whppt-form-textarea textarea {
  width: 100%;
  padding: 1rem;
  font-size: 1.125rem;
  font-weight: 500;
}
</style>
