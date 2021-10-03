<template>
    <div :style="basicStyle">
        <form :style="myStyle">
            <input type="text" :style="textStyle" placeholder="오늘 할 일을 입력해주세요." 
            @keydown.enter.prevent="submit" v-model="todo"/>
        </form>
    </div>
</template>

<script>
import { inputTodo } from "../main";
export default{
    data(){
        return{
            todo: '',
            basicStyle:{
                width: "100%",
            },
            myStyle:{
                display: "flex",
                width: "300px",
                height: "45px",
                margin: "0 auto",
                backgroundColor: "#ffffff",
                borderRadius: "20px",
            },
            textStyle:{
                width: "100%",
                border: 0,
                outline: 0,
                padding: "3px 30px 3px 17px",  
            }
        }
    },
    methods:{
        check(){
            console.log("click");
        },
        submit(){
            console.log(this.todo)
            inputTodo.$emit('userInput', this.todo);
            this.todo=""
        }
    }
}
</script>

<style scoped>
    input[type='text']::placeholder{
        text-align: center;
    }
</style>
