<template>
    <div class="input">
        <input class="input__text" type="text" :placeholder="placeholder" @input="input" required>
    </div>
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

<style lang="scss">
.input {
    position: relative;
    color: $black;
    &::after {
        content: "";
        position: absolute;
        bottom: -2px;
        left: 0;
        width: 100%;
        height: 2px;
        background-color: rgba(0, 0, 0, 0.1);
    }

    &__text {
        width: 100%;
        outline: none;
        border: none;
        padding-bottom: $xs;
        // font-family: $primary-font;
        // font-size: $sm;
    }

    // &__select{
    //     width: 100%; //text ile aynı oldu
    //     border: none;
    //     outline: none;
    //     padding-bottom: 10px;
    //     font-size: 18px;
    // }
}
</style>