<template>
    <div class="formInfo">
        <h1 class="formTitle">Post Your Requirements</h1>
        <h2 class="formText">Please fill the form below to receive a quote for workspace. <br> Please add all the details required.</h2>
    </div>
    <div class="ContactWindow">
        <div class="Details">
            <h1 class="detailsTitle">Contact details</h1>
            <p class="detailsText">Please fill your information so we can get in touch with you.</p>
        </div>
        <Input v-model="internalValue" :inputList="inputList"/>
    </div>
</template>

<script>
    import Input from '../ui/input.vue'

    export default {
        data(){
            return{
                inputList:[
                {id:1,title: 'Name', type: 'Text',  placeholder: 'Your Name'},
                {id:2,title: 'Phone Number', type: 'tel',  placeholder: '(123) 456 - 7890'},
                {id:3,title: 'Email', type: 'Text',  placeholder: 'Your Mail ID'},
                {id:4,title: 'Date', type: 'date',  placeholder:'dd - mm - yyyy'},
                ],
                internalValue: this.modelValue,
            }
        },
        components:{
            Input
        },
        props:['modelValue'],
        watch:{
            value(newVal){
                if(this.internalValue !== newVal){
                    this.internalValue = newVal
                }
            },
            internalValue(newVal){
                this.$emit('update:modelValue', newVal)
            }
        }
    }
</script>

<style>
    .formInfo{
        display: flex;
        flex-direction: column;
        align-items: center;

    }
    .formTitle{
        font-size: 34px;
        font-weight: 700;
        line-height: 46px;
        margin: 0;
        margin-bottom: 12px;
    }
    .formText{
        font-size: 18px;
        font-weight: 500;
        text-align: center;
        margin: 0;
        margin-bottom: 42px;
        line-height: 30px;
        color: #6F6C90;
    }
    .detailsTitle{
        font-size: 24px;
        font-weight: 700;
        line-height: 35px;
        margin-top: 24px;
        margin-bottom: 6px;
    }
    .detailsText{
        font-size: 18px;
        font-weight: 500;
        line-height: 30px;
        margin-top: 0px;
        margin-bottom: 18px;
        color: #6F6C90;
    }
    .ContactWindow{
        width: 700px;
        height: 808px;
        border-radius: 34px;
        border: 1px solid #EFF0F6;
        background: #FAF8F8;

        box-shadow: 0px 5px 16px 0px rgba(8, 15, 52, 0.06);

        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .Details{
        width: 595px;
        height: 111px;
        text-align: left;
        border-bottom: 1px solid #D9DBE9;
        padding-left: 18px;
    }
</style>