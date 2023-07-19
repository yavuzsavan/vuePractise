<template>
    <form class="form">
        <!-- <p class="title">Send Us a Message</p> -->
        <Title :titleText="titleText"></Title>
        <InputText v-model="formData.userName" :placeholder="placeholder"></InputText>
        <InputText v-model="formData.userEmail" :placeholder="placeholder2"></InputText>
        <!-- <input v-model="formData.userName" class="input" placeholder="Full Name"> -->
        <!-- <input v-model="formData.userEmail" class="input" placeholder="Your Email"> -->
        <!-- <select v-model="formData.userAction" class="select">
            <option v-for="option in options" :key="option.value" class="select__option">{{ option }}</option> 
        </select> -->
        <!-- how to v-bind --> 
        <InputSelect v-model="formData.userAction" :options="options"></InputSelect>
        <!-- <textarea v-model="formData.userText" class="textarea" placeholder="Your message goes here..."></textarea> -->
        <Textarea v-model="formData.userText" :placeholder="placeholder3"></Textarea>
        <Button :buttonText="buttonText" @click="submitForm" class="btn"></Button>
    </form>
</template>

<script>
import Button from "@/components/Button";
import Title from "@/components/Title"; // input select textarea component ?
import InputText from "@/components/InputText";
import InputSelect from "@/components/InputSelect";
import Textarea from "@/components/Textarea";

export default {
    name: "Form",
    components: { Button, Title, InputText, InputSelect, Textarea },
    data() {
        return {
            titleText: "Send Us a Message",
            buttonText: "Submit form",
            placeholder: "Full Name",//prop olarak geçmeye gerek var mı
            placeholder2: "Your Email",
            placeholder3: "Your message goes here...",
            formData: {
                userName: "",
                userEmail: "",
                userAction: "",
                userText: ""
            },
            options: [
                {value: "post", label: "I want to post"}, 
                {value: "a", label: "A"},
                {value: "b", label: "B"},
                {value: "c", label: "C"}],
        }
    },
    methods: {
        submitForm() {
            console.log(this.formData);
        },
    }
}
</script>

<style lang="scss" scoped>  
// where to write these scss ?
$ebony: #151534;
$white: #FFF;
$mercury: #E6E6E6;

$primary-font: IBM Plex Sans;
$secondary-font: Merriweather;

$fs-sm: 18px;
$fs-md: 20px;
$fs-lg: 24px;

$fw-sm: 500;
$fw-md: 700;

.form {
    display: flex;
    flex-direction: column;
    gap: 50px;
    background-color: $white;
    padding: 65px;
    margin-top: 50px;
    border-radius: 25px;
    box-shadow: 0px 24px 35px -15px rgba(100, 93, 152, 0.17);
}

.title{
    color: $ebony;
    font-family: $secondary-font;
    font-size: $fs-lg;
    font-weight: $fw-md;
}

.input{

}

.select{
    &__option{

    }
}

.textarea{
    width: 476px;
    height: 159px;
    border-radius: 10px;
    border: 2px solid $mercury;
    background: $white;
    padding: 30px;
}

.btn{
    padding: 20px;
    border-radius: 70px;
    cursor: pointer;
    font-family: $secondary-font;
    font-size:  $fs-md;
    font-weight: $fw-sm;
    color: $white;
    background: $ebony;
}
</style>