<template>
    <div class="mainBody">
        <h1 class="titleUsd">USD Best Price in Brazil</h1>

        <p class="txtSub">Compare and find in realtime the best effective prices in Brazil's top USD exchanges, considering fees. <br> <span>Click on the exchange row</span> to view operation details.</p>
        <CurrencyController/>
    </div>
</template>
<script>
import CurrencyController from './CurrencyController'

export default {
    components: { CurrencyController }
}
</script>

<style lang="scss">
    .mainBody {
        margin-top: 150px;
    }

    .titleUsd{
        font-weight: 300;
        color: #003358;
        font-size: 52px;
    }
    .txtSub {
        font-size: 18px;
        line-height: 32px;
        text-align: center;
        letter-spacing: 0.015em;
        color: #585858;
        opacity: 0.8;
        span {
            background: #EFEFEF;
            border: 1px solid #BEBEBE;
            box-sizing: border-box;
            border-radius: 8px;
            padding: 6px 10px;
        }
    }
    @media screen and (max-width: 629px){
        .titleUsd {
        font-size: 40px;
        margin: 0 3%;
        }
        .txtSub {
            margin: 0 3%;
        }
    }
    @media screen and (max-width: 329px){
        .mainBody {
            margin-top: 110px;
        }
    }
</style>