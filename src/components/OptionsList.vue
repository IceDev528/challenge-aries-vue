<template>
  <div class="input-options-wrapper">
    <h2>Options</h2>
    <ul>
      <li v-for="(option, index) in options" :key="index">
        Type: {{ option.type }}, Long or Short: {{ option.long_short }}, Price:${{
          option.strike_price
        }}, Bid: ${{ option.bid }}, Ask: ${{ option.ask }}
      </li>
    </ul>
    <button @click="updateOptions">Generate Graph</button>
  </div>
</template>

<script>
export default {
  props: ["options"],
  methods: {
    updateOptions() {
      this.$emit("update-options", this.options);
    },
  },
};
</script>

<style scoped>
.input-options-wrapper {
  text-align: left;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>
