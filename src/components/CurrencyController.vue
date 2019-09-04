<template>
    <div class="container">

        <div v-if="errorLoad">
            <h1>Oops... something's wrong. please refresh and try again</h1>
        </div>
        <div v-if="dolarCalc >= 0 && !errorLoad">
            <CurrencyInput :label="'BRL'" @update-currency="brlUpdate" ref="brl"/>
            <CurrencyInput :label="'USD'" @update-currency="usdUpdate" ref="usd"/>
        </div>
    </div>
</template>
<script>
import CurrencyInput from './CurrencyInput/CurrencyInput'

export default {
    components: { CurrencyInput },
    data () {
        return {
            dolarCalc: 0,
            errorLoad: false            
        }
    },
    methods: {
        brlUpdate (v) {
            this.$refs['usd'].cmodel = this.calcNumber(v, '/')
        },
        usdUpdate (v) {
            this.$refs['brl'].cmodel = this.calcNumber(v, '*')
        },
        calcNumber (num, op) {
            let n = num.replace(',', '.')
            let ret = (op === '*')? parseFloat(n * this.dolarCalc).toFixed(2) : parseFloat(n / this.dolarCalc).toFixed(2)
            return `${ret}`.replace('.', ',')
        }
    },
    created () {
        this.$http.get('https://economia.awesomeapi.com.br/all/USD-BRL').then(s => {
            this.dolarCalc = `${parseFloat(s.data.USD.ask.replace(',', '.')).toFixed(2)}`
            this.$refs['brl'].cmodel = `${this.dolarCalc}`.replace('.', ',')
            this.$refs['usd'].cmodel = '1,00'
        }, () => {
            this.errorLoad = true
        })
    } 
}
</script>
<style lang="scss">
    .container {
        margin-top: 70px;
    }
    @media screen and (max-width: 629px){
      .container {
        margin-top: 20px;
    }  
    }
</style>