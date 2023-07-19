<template>
  <select class="select" v-bind="$attrs" v-model="selectedOption">
    <option v-for="option in options" :key="option.value" :value="option.value">{{ option.label }}</option>
  </select>
</template>

<script>
export default {
    name: "InputSelect",
    props: {
        options: {
            type: Array,
            required: true,
        },
        value: {
            required: true,
        }
    },
    computed: {
        selectedOption: {
            get() {
                return this.value;
            },
            set(newValue) {
                this.$emit("input", newValue);
            }
        },
    },
//     methods: {
//         toggle() {
//             this.isOpen = !this.isOpen;
//         },
//         handleClick() {
//             this.selectedOption = optionValue
//             this.isOpen = false;
//         }
//     },
//     watch: {
//         value(newValue) {
//             this.selectedOption = newValue;
//         }
//     }
}
</script>

<style lang="scss" scoped>

</style>