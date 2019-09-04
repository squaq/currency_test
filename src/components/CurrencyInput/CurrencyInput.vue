<template>
    <div class="containerInputs">
        <div class="currencyInput">
            <input type="text" v-model="cmodel" @input="updateCurrency"> 
            <div class="lineLabel"></div>
            <div class="txtLabel">{{label}} <img v-if="label !== 'USD'"  src="./imgs/arrow.png" class="arrowDown"></div>
        </div>
    </div>
</template>
<script>
export default {
    props: ['label'],
    data() {
        return {
            cmodel: 0

        }
    },
    methods: {
        updateCurrency () {
            this.$emit('update-currency', this.cmodel)
        }
    },
    created () {
    }
}
</script>
<style lang="scss">
.containerInputs {
    display: inline-block;
    margin: 8px;
}
.currencyInput {
    border: 2px solid rgba($color: #585858, $alpha: 0.2);
    box-sizing: border-box;
    border-radius: 16px;
    display: flex;
    width: 290px;
    
    input {
        font-size: 28px;
        line-height: 33px;
        text-align: right;
        color: #585858;
        border: none;
        background: transparent;
        display: inline-block;
        max-width: 170px;
    }

    .lineLabel{
        width: 2px;
        height: 48px;
        background: #585858;
        opacity: 0.2;
        display: inline-block;
        margin: 14px 2px 14px 10px;
    }
    .txtLabel {
        font-weight: bold;
        font-size: 28px;
        line-height: 76px;
        color: #003358 !important;
        flex: auto;
    }

}
@media screen and (max-width: 629px){
    .containerInputs {
        display: block;
        width: 90%;
        margin-left: auto;
        margin-right: auto;

    }
    .currencyInput{
        width: 100%;
    }
}
</style>