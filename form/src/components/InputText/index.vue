<template>
    <input class="input"
    type="text"
    :placeholder="placeholder"
    @input="input">
</template>

<script>
export default {
    name: "InputText",
    props: {
        //inputVal: String,// gerek var mı yukarıda :value="inputVal"
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

</style>