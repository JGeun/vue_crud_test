<template>
  <div v-bind:style="parentStyle">
    <div :style="areaStyle"><span :style="titleStyle">{{title}}</span></div>
    <Inputs :style="{'position': 'relative'}"/>
    <TodoLists/>
  </div>
</template>

<script>
  import Inputs from './Input.vue';
  import TodoLists from './TodoList.vue';
  export default {
    components:{
        Inputs, TodoLists
    },
    data(){
      return{
        title: "JGeun의 ToDo리스트",
        parentStyle:{
          width: "100%",
          height: "100px",
          marginTop: "250px",
        },
        areaStyle:{
          display: "flex",
          width: "700px",
          height: "100%",
          margin: "0 auto",
          justifyContent: "center",
          alignItems: "center",
        },

        titleStyle:{
          fontSize: "50px",
          textAlign: "center",
          padding: "10px 20px"
        }
      }
    },
  }
</script>
