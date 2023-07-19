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

</style>