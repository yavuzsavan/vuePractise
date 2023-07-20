<template>
    <textarea class="textarea" :placeholder="placeholder" @input="input" required></textarea>
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

<style lang="scss" scoped>
.textarea {
    width: 476px; //width & height how to do with out giving specific % or any
    height: 159px;
    @include border(2px, solid, $mercury, $b-sm);
    background: $white;
    padding: $md;
}
</style>