<template>
    <div class="Banner">
        <div class="banner">
            <img src="../assets/_Home_Banner.svg" />
        </div>
        <div class="content">
            <h1>Plasma IDE</h1>
            <p>A Project By Axeri</p>
        </div>
    </div>
</template>

<style lang="less">
    @import "../assets/scheme.less";

    .Banner {
        width: 100%;
        height: 300px;
        overflow: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
        background: @layer0;
        position: relative;

        .banner img {
            min-width: 100%;
            min-height: 100%;
            position: absolute;
            top: 0px;
            left: 0px;
            opacity: 0.3;
        }

        .content {
            position: absolute;
            color: @contrastColor;
            display: flex;
            flex-direction: column;
            font-family: @mainFont;
            align-items: center;
            h1 {
                margin: 0px;
                font-weight: lighter;
                font-size: 30px;
            }
            p {
                font-size: 13px;
                opacity: 0.7;
                margin: 0px;
            }
        }

        @media (max-width: 1000px) {
            height: 200px;
        }
        @media (max-width: 500px) {
            height: 150px;
            .content {
                h1 {
                    font-size: 20px;
                }
                p {
                    font-size: 11px;
                }
            }
        }
    }
</style>