<template>
    <form class="form">
        <!-- <p class="title">Send Us a Message</p> -->
        <Title :titleText="titleText"></Title>
        <InputText v-model="formData.userName" :placeholder="placeholder" class="input"></InputText>
        <InputText v-model="formData.userEmail" :placeholder="placeholder2" class="input"></InputText>
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
            placeholder: "Full Name",//prop olarak geçmeye gerek var mı & böle olmaz bu iş
            placeholder2: "Your Email",
            placeholder3: "Your message goes here...",
            formData: {
                userName: "",
                userEmail: "",
                userAction: "",
                userText: ""
            },
            options: [
                { value: "post", label: "I want to post" },
                { value: "a", label: "A" },
                { value: "b", label: "B" },
                { value: "c", label: "C" }],
        }
    },
    methods: {
        submitForm() {
            console.log(this.formData);
        },
    }
}
</script>

<style lang="scss" scoped>  // where to write these scss ?
  .form {
    // @include flex(column, $lg); // didnt work
      display: flex;
      flex-direction: column;
      gap: $lg;
      background-color: $white;
      padding: $xl;
      margin-top: $lg;
      border-radius: $b-md;
      box-shadow: $shadow;
  }
</style>