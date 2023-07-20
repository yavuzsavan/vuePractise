<template>
    <div>
        <Form></Form>
    </div>
</template>

<script>
import Form from "@/components/Form";
export default {
    name: 'FormView',
    data() {
        return {

        }
    },
    components: {Form},
}
</script>

<style lang="scss" scoped>

div{
    @include flex(row, 0, center);
    background-color: $selago;
}
</style>