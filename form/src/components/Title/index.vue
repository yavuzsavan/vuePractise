<template>
    <p class="title">{{ titleText }}</p>
</template>

<script>
export default {
    name: "Title",
    props: {
        titleText: String,
    },
}
</script>

<style lang="scss" scoped>
.title {
    color: $ebony;
    font-family: $secondary-font;
    font-size: $fs-lg;
    font-weight: $fw-md;
}
</style>