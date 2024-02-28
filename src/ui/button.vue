<template>
    <button class="uiElem" @click="inputLog">{{ this.title }}</button>
</template>

<script>
    export default{
        props:['title'],
        emits:['inputLog'],
        methods:{
            inputLog(){
                this.$emit('inputLog')
            }
        }
    }
</script>

<style>
    .uiElem{
        display: inline-flex;
        padding: 20px 40px 21px 40px;
        justify-content: center;
        align-items: center;
        gap: 8px;
        border-radius: 56px;
        background: linear-gradient(180deg, #9E96F2 0%, #EC31F0 100%);
        box-shadow: 0px 3px 12px 0px rgba(74, 58, 255, 0.18);
        color: white;
        font-size: 24px;
        font-weight: 700;
        line-height: 20px;
        border: 0px;
        margin-top: 68px;
        margin-bottom: 265p;
    }
</style>