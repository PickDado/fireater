<template>

    <div>
        <div>
        <select select id="SelectDay" name="Data" @click="select()" @keyup="select()" >
        <option>- Seleziona un giorno specifico -</option>
        <option value="2020-08-21">21/08/2021</option>
        <option value="2020-08-22">22/08/2021</option>
        <option value="2020-08-23">23/08/2021</option>
        <option value="2020-08-24">24/08/2021</option>
        <option value="2020-08-25">25/08/2021</option>
        <option value="2020-08-26">26/08/2021</option>
        <option value="2020-08-27">27/08/2021</option>
        <option value="2020-08-28">28/08/2021</option>        
    </select>
        </div> 

    <div>
        <CheckExtract :compare="DataSelected" />
    </div>

    </div>
</template>

<script>


export default {
    components:{
        
    },

    data(){return{
        DataSelected:"- Seleziona un giorno specifico -",
    }},
   methods:{
       select(){
           this.DataSelected=document.querySelector("#SelectDay").value;
       }
   }
}
</script>

<style scoped>
select{
    font-size:x-large;
    text-align: center;
    margin-block-start: 0%;
    padding-block-start: 0%;
}


</style>