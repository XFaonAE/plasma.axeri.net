<template>
    <div class="Banner">
        <div class="banner">
            <div class="animation">
                <div></div>
                <div></div>
                <div></div>
                <div></div>
                <div></div>
                <div></div>
                <div></div>
            </div>
        </div>
        <div class="content">
            <h1>Plasma IDE</h1>
            <p>A Project By Axeri</p>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            this.$el.parentNode.parentNode.addEventListener("scroll", () => {
                this.$el.querySelector(".banner .animation").style["margin-top"] = (this.$el.parentNode.parentNode.scrollTop / 2) + "px";
            });
        }
    }
</script>

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

        .banner .animation {
            min-width: 100%;
            min-height: 100%;
            position: absolute;
            top: 0px;
            left: 0px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: @contrastColor;

            div:nth-child(1) {
                width: 250px;
                height: 250px;
                border-radius: 100%;
                border: 2px solid @layer5;
                border-top-color: transparent;
                position: absolute;
                animation-name: BannerAnimateLeftSpin;
                animation-duration: 45s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(2) {
                width: 220px;
                height: 220px;
                border-radius: 100%;
                border: 2px solid @layer3;
                border-top-color: transparent;
                position: absolute;
                animation-name: BannerAnimateLeftSpin;
                animation-duration: 35s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(3) {
                width: 190px;
                height: 190px;
                border-radius: 100%;
                border: 2px solid @layer3;
                border-bottom-color: transparent;
                border-left-color: transparent;
                position: absolute;
                animation-name: BannerAnimateLeftSpin;
                animation-duration: 45s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(4) {
                width: 270px;
                height: 270px;
                border-radius: 100%;
                border: 2px solid @layer3;
                border-bottom-color: transparent;
                border-right-color: transparent;
                position: absolute;
                animation-name: BannerAnimateLeftSpin;
                animation-duration: 75s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(5) {
                width: 300px;
                height: 300px;
                border-radius: 100%;
                border: 2px solid @layer5;
                border-bottom-color: transparent;
                border-top-color: transparent;
                position: absolute;
                animation-name: BannerAnimateLeftSpin;
                animation-duration: 105s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(6) {
                width: 470px;
                height: 470px;
                border-radius: 100%;
                border: 2px solid @layer3;
                border-bottom-color: transparent;
                border-right-color: transparent;
                border-left-color: transparent;
                position: absolute;
                animation-name: BannerAnimateRightSpin;
                animation-duration: 45s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            div:nth-child(7) {
                width: 500px;
                height: 500px;
                border-radius: 100%;
                border: 2px solid @layer3;
                border-right-color: transparent;
                border-left-color: transparent;
                position: absolute;
                animation-name: BannerAnimateRightSpin;
                animation-duration: 45s;
                animation-iteration-count: infinite;
                animation-timing-function: linear;
            }

            @keyframes BannerAnimateLeftSpin {
                from {
                    transform: rotate(0deg);
                }

                to {
                    transform: rotate(360deg);
                }
            }

            @keyframes BannerAnimateRightSpin {
                from {
                    transform: rotate(0deg);
                }

                to {
                    transform: rotate(-360deg);
                }
            }
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