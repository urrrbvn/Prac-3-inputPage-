<template>
<div class="InputCont" v-for="elem in inputList">
    <h3>{{ elem.title }}</h3>
    <input v-if="elem.type !== 'tel'"   class="inputItem" 
                                        :type="elem.type"
                                        :placeholder="elem.placeholder"
                                        :id="elem.id"
                                        @input="changeProp($event.target.value , elem.id)">
    <input v-else   class="inputItem" 
                    pattern="2[0-9]{3}-[0-9]{3}"
                    :type="elem.type"
                    :placeholder="elem.placeholder"
                    :id="elem.id"
                    @input="changeProp($event.target.value , elem.id)">
</div>    
</template>

<script>
    export default{
        data(){
            return{
                changeVal:'',
                InternalVal:this.modelValue,
                keys: Object.keys(this.modelValue)
            }
        },
        props:[
            'inputList','modelValue'
        ],
        methods: {
            onInput(event) {
            this.$emit('update:modelValue', event.target.value);
        },
        changeProp(value,id){
                this.modelValue[this.keys[(id-1)]] = value                
            }
        },
        watch:{
            InternalVal(newVal){
                this.$emit('update:modelValue', newVal)
            }
        }
}
</script>

<style>
    .InputCont{
        width: 284px;
        height: 104px;
        align-self: flex-start;
        text-align: left;
        text-align: start;
        margin-top: 48px;
        margin-left: 64px;

    }
    .inputItem{
        width: 264px;
        height: 66px;
        border-radius: 46px;
        border: 1px solid var(--Neutral-300, #EFF0F6);
        background: var(--Neutral-100, #FFF);
        box-shadow: 0px 2px 6px 0px rgba(19, 18, 66, 0.07);
        padding: 0;
        padding-left: 20px;

    }
    h3{
        margin-top: 0;
        margin-bottom: 16px;
        line-height: 20px;
    }
</style>