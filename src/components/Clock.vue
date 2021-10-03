<template>
  <div :style="areaStyle">{{now}}</div>
</template>

<script>
export default{
    data(){
        return{
            now: "00:00:00",
            areaStyle:{
                position: "absolute",
                top: "30px",
                right: "30px",
                fontSize: "30px",
            }
        }  
    },
    created(){
        const hours = String(new Date().getHours()).padStart(2, "0")
        const minutes = String(new Date().getMinutes()).padStart(2, "0")
        const seconds = String(new Date().getSeconds()).padStart(2, "0")
        this.now = `${hours} : ${minutes} : ${seconds}`
        this.showClock()
    },
    methods: {
        showClock(){
            setInterval(() => {
                const hours = String(new Date().getHours()).padStart(2, "0")
                const minutes = String(new Date().getMinutes()).padStart(2, "0")
                const seconds = String(new Date().getSeconds()).padStart(2, "0")
                this.now = `${hours} : ${minutes} : ${seconds}`
            }, 1000);
        }
    },
}

</script>
