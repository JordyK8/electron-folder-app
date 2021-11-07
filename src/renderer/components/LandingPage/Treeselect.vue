<template>
  <div>
  <treeselect
    :multiple="true"
    :options="options"
    placeholder="Select your favourite(s)..."
    v-model="value"
    />
  <treeselect-value :value="value" />
</div>
</template>

<script>
import Treeselect from '@riophae/vue-treeselect';

export default {
  components: { Treeselect },
  props: ['options'],
  created() {
    console.log(this.items);
  },
  data: () => ({
    value: [],
  }),
  watch: {
    value(val) {
      if (val) {
        this.$emit('addFolder', val);
      }
    },
  },
};
</script>

<style src="@riophae/vue-treeselect/dist/vue-treeselect.min.css"></style>