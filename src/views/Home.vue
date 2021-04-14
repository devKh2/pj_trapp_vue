<template>
    <div>
        <h1>Welcome to {{title2}}!</h1>
        <input type="text" v-model="city">
        <button type="button" @click="getData">Get</button>
        <button type="button" @click="setData('Barcelona')">Set</button>
        <select class="form-control" v-model="region" @change="changeRegion">
            <option :key="i" :value="d.v" v-for="(d,i) in options">{{d.t}}</option>
        </select>

        <table class="table table-bordered" v-if="tableShow">
            <tr :key="i" v-for="(d,i) in options">
                <td>{{d.v}}</td>
                <td>{{d.t}}</td> 
            </tr>
        </table>
        
    </div>
</template>
<script>
export default {
    data(){
        return {
            title : "김현호",
            title2 : "와르",
            city : "Busan",
            options : [
                {v:"S",t:"Seoul"},
                {v:"B",t:"Busan"},
                {v:"D",t:"Daejeon"},
            ],
            region : "B",
            tableShow : true,
        };
    },
    watch : {
      city(){
          console.log(this.city);
      },
      title(){

      }
    },
    methods : {
        getData(){
            alert(this.city);
        },
        setData(n_city){
            this.city=n_city;
        },
        changeRegion(){
            alert(this.region);
        }
    },

    beforeCreate() {
        console.log("beforeCreate");
    },
    created() {
        console.log("created");
    },
    beforeMount() {
        console.log("beforeMount");
    },
    mounted() {
        console.log("mounted");
    },
    beforeUpdate() {
        // console.log("beforeUpdate");
    },
    updated() {
        // console.log("updated");
    },
    beforeDestroy() {
        console.log("beforeDestroy");
    },
    destroyed() {
        console.log("destroyed");
    },
};
</script>