<template>
  <div :style="areaStyle">
    <ul :style="ulStyle">
      <li :style="liStyle" @click="deleteLi(index)" v-for="(item, index) in items" :key="index">{{index + " : " +item.text}}</li>
    </ul>
  </div> 
</template>

<script>
import {inputTodo} from "../main";
    export default{
        data: () => ({
            todo : "",
            selectedItem: 1,
            items: [
                { text: 'Vue 공부하기'},
                { text: 'Spring Boot 듣기'},
                { text: '과제 하기'},
            ],

            areaStyle:{
              position:'relative',
              margin: '20px auto',
              display: "block",
              borderRadius: "20px",
              width: "400px",
              height: "600px",
              backgroundColor: "#F2F9FB"
            },

            ulStyle:{
              listStyle: "none",
              padding: "10px 0",
              height: "100%",
              textDecoration: "none"
            },

            liStyle:{
              display: "block",
              padding: "5px 20px",
              textDecoration: "none"
            }
        }),
        methods: {
          deleteLi: function(index){
            this.$delete(this.items, index)
          }
        },
        created(){
          inputTodo.$on('userInput', getTodo => {
            var obj = new Object();
            obj.text = getTodo;
            this.items.push(obj);
          })
        }        
    }
</script>

<style scoped>
  li:hover{
    background-color: #FFABA8;
  }
</style>
