<template>
    <textarea class="textarea" :placeholder="placeholder"
    @input="input"></textarea>
</template>

<script>
export default {
    name: "Textarea",
    props: {
        placeholder: String,
    },
    methods: {
        input() {
            this.$emit("input", event.target.value);
        }
    }
}
</script>

<style lang="scss" scoped></style>