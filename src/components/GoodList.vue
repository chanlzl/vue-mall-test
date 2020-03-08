<template>
    <div name="show">
        <ul class="goodlist">
            <li v-for="goods in list" :key="goods">
                <img v-bind:src="goods.img">
                <p>{{goods.goodName}}</p>
            </li>
        </ul>
    </div>
</template>
<style>
    .goodlist li
    {
        width: 200px;
        height: 200px;
        list-style: none;
        float: left;
        font-size: 12px;
        color: red;
        margin-bottom: 30px;
    }
    .goodlist img
    {
        width: 180px;
        height: 180px;
    }
</style>
<script>
export default {
    name:"show",
    data(){
        var obj=this;
        var url="";
        if(obj.goodId==1){
            url="json/pc.json";
        }
        else if(obj.goodId==2)
        {
            url="json/phone.json";
        }
        else
        {
            url="json/pc.json";
        }
        this.$http.get(url).then(function(res){
            obj.list=res.data;
        })
        return{
            list:[]
        }
    },
    props:
    {
        goodId:Number
    },
    watch:
    {
        goodId()
        {
            var obj=this;
            var url="";
            if(obj.goodId==1){
                url="json/pc.json";
            }
            else if(obj.goodId==2)
            {
                url="json/phone.json";
            }
            else
            {
                url="json/pc.json";
            }
            this.$http.get(url).then(function(res){
            obj.list=res.data;
            })
            return
            {
                list:[]
            }
        }
    }
}
</script>