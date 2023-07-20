<template>
    <div class="input">
        <select class="input__text" v-bind="$attrs" v-model="selectedOption" required>
            <option v-for="option in options" :key="option.value" :value="option.value" class="input__text__option">{{
                option.label }}</option>
        </select>
    </div>
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
        },
    },
    computed: {
        selectedOption: {
            get() {
                return this.value;
            },
            set(newValue) {
                this.$emit("input", newValue);
            },
        },
    },
}
</script>

<style lang="scss" scoped></style>