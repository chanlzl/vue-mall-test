<template>
    <div>
        <div v-if="ll==1">
            <GoodList :goodId="1"></GoodList>
        </div>
        <div v-else-if="ll==2">
            <GoodList :goodId="2"></GoodList>
        </div>
        <div v-else-if="ll==3">
            3333
        </div>
        <div v-else-if="ll==4">
        </div>
        <div v-else>
            <GoodList></GoodList>
        </div>
    </div>
</template>
<script>
import Msg from './Msg.js'
import GoodList from './GoodList.vue'
export default 
{
    data(){
        return{
            ll:0
        }
    },
    mounted:function()
        {
            var _this=this
            Msg.$on('val',function(m)
                {
                    _this.ll=m;
                })
        },
        components:{
            GoodList
        }
}
</script>