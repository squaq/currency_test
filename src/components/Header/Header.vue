<template>
    <nav>
        <div class="logo">
            <img src="./imgs/bleutest.png" alt="">
        </div>

        <div class="right-ops" >
            <a>Bleutest Buy</a>
            <a class="disabled">Compare</a>
            <a>Remittance</a>
            <a>Exchanges</a>
            <a>Exchanges' Fees</a>
            <a class="loginBtn">Login</a>
            <a> 
                <!-- <img src="./imgs/bra.svg" alt="">  -->
                <span>BRL</span> 
                <!-- <img src="./imgs/arrow-down.svg" alt=""> -->
            </a>
            <a href="" class="menuIcon">
                <div class="dots"></div>
                <div class="dots"></div>
                <div class="dots"></div>
            </a>
        </div>

    </nav>
    
</template>
<style lang="scss">
    nav{
        position: absolute;
        height: 100px;
        left: 0px;
        right: 0px;
        top: 0px;
        background: #0080DD;
        color: #fff;
    }
    .logo { 
        margin-top: 35px;
        padding-left: 10%;
        float: left;
    }
    .right-ops {
        float: right;
        padding-right: 10%;
        margin-top: 44px;
        a {
            font-size: 16px;
            text-align: center;
            margin-right: 32px;
            padding-bottom: 8px;
            font-weight: bold;
            cursor: pointer;
        }
        a.disabled, a:hover {
            border-bottom: solid 2px #fff;
        }
        a.disabled {
            pointer-events: none;
        }
    }
    a.loginBtn {
        border: solid 2px #fff;
        padding: 6px 14px;
        border-radius: 12px;
        &:hover {
            background-color: #003358;
        }
    }

    .menuIcon {
        display: none;
        .dots {
            background-color: #fff;
            width: 10px;
            height: 10px;
            margin-bottom: 5px;
            border-radius: 5px;
        }
        &:hover {
            border-bottom: none !important;
        }
    }

    @media screen and (max-width: 1230px){
        .logo { 
            padding-left: 3%;
        }
        .right-ops {
            padding-right: 3%;
            a {
                margin-right: 22px;
            }
        }
    }

    @media screen and (max-width: 959px){
        .right-ops {
            margin-top: 30px;
            a {
                display: none;
            }
            .menuIcon { display: inline-block}
        }
    }

</style>