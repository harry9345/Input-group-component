<template>
  <ul>
    <li :class="{active: modelValue ==='poor'}">
      <button type="butto" @click="activate('poor')">Poor</button>
    </li>
    <li :class="{active: modelValue ==='avrage'}">
      <button type="butto" @click="activate('avrage')">Avrage</button>
    </li>
    <li :class="{active: modelValue ==='great'}">
      <button type="butto" @click="activate('great')">Great</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['modelValue'],
  emits: ['update:modalValue'],
  //   data() {
  //     return {
  //       activeOption: this.modelValue
  //     };
  //   },
  // computed:{
  //     activeOption(){}
  // },
  methods: {
    activate(option) {
      this.$emit('update:modalValue', option);
    }
  }
};
</script>

<style scoped>
.active {
  border-color: tomato;
}
.active button {
  background-color: thistle;
}
ul {
  list-style: none;
  margin: 0, 5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 2px solid red;
  padding: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
}
button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>