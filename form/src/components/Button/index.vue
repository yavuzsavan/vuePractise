<template>
    <button @click="click" class="btn">{{ buttonText }}</button>
</template>

<script>
export default {
    name: "Button",
    props: {
        buttonText: String,
    },
    methods: {
        click() {
            this.$emit("click");
        },
    }
}
</script>

<style lang="scss" scoped>
.btn {
    padding: $sm;
    border-radius: $b-lg;
    cursor: pointer;
    font-family: $secondary-font;
    font-size: $fs-md;
    color: $white;
    background: $ebony;
}
</style>