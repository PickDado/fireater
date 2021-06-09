<template>
    <div>
        <h2 v-if="!loading">N° incendi in data selezionata: {{nOfFidre}}</h2>
        <h1 v-if="loading">Caricamento in corso...</h1>
        <!-- <h1 v-if="!loading">{{Result}}</h1> -->
    <FireMap2 v-if="!loading" :dati="Result"/>
    </div>
</template>

<script>

export default {
    name:"CheckExtract",
    components:{
       
    },
    data(){return{
        AllData:[],
        Result:[],
        loading:true,
    }},

    props:["compare"],

    watch:{
        compare:function(){
            if(this.compare !="- Seleziona un giorno specifico -"){
                this.Result=[];
            for(let i = 0;i < this.AllData.length;i++ ){
                if(this.AllData[i].date==this.compare){
                    this.Result.push(this.AllData[i]);
                }
            }}
            else this.Result=this.AllData;
        },

        Result:function(){
            if (this.Result != [])
            this.loading=false}
    },
    computed:{
        nOfFidre: function(){
            return this.Result.length
        }
    },
    created :function(){
         fetch("https://api.npoint.io/9155237c5f3406e1c54d").then(function(fireArray){            
            return fireArray.json()            
        }
        ).then((risp)=>{
            this.AllData=risp;
            this.Result=risp; 
            console.log(risp);
        }
        );
    },
}
</script>