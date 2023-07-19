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
    display: flex;
    justify-content: center;
    background-color: #F5F5FD;
}
</style>