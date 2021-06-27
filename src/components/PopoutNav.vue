<template>
    <div class="PopoutNav">
        <div class="header">
            <span>Menu</span>

            <button>
                <Icon icon="ChromeClose" />
            </button>
        </div>

        <div class="links">
            <RouterLink to="/">Home</RouterLink>

            <RouterLink to="/download">Download</RouterLink>

            <RouterLink to="/github">GitHub</RouterLink>

            <RouterLink to="/about">About</RouterLink>
        </div>
    </div>
</template>

<script>
    import Icon from "./Icon.vue";

    export default {
        components: {
            Icon
        }
    }
</script>

<style lang="less">
    @import "../assets/scheme.less";

    .PopoutNav {
        width: 250px;
        height: 100vh;
        background: @layer2;
        display: flex;
        position: fixed;
        top: 0px;
        flex-direction: column;
        left: -250px;
        transition-duration: @animateSpeed;

        .links {
            display: flex;
            flex-direction: column;

            a {
                color: @contrastColor;
                font-family: @mainFont;
                opacity: 0.6;
                font-size: 13px;
                transition-duration: @animateSpeed;
                text-decoration: none;
                padding: 9px 20px;
                border-left: 1px solid transparent;
                padding-right: 21px;

                &:hover {
                    opacity: 1;
                    background: @layer3;
                }

                &.router-link-active {
                    border-color: @accentColor;
                    opacity: 1;
                }
            }
        }

        .header {
            width: 100%;
            height: 40px;
            padding: 0px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: @layer1;

            span {
                color: @contrastColor;
                font-family: @mainFont;
                font-size: 13px;
            }

            button {
                border: none;
                height: 40px;
                padding: 0px 10px;
                margin-right: -10px;
                transition-duration: @animateSpeed;
                cursor: pointer;
                color: @contrastColor;
                background: transparent;

                i {
                    transform: scale(0.7);
                }

                &:hover {
                    background: @layer2;
                }
            }
        }

        &:after {
            content: "";
            display: flex;
            width: calc(100vw - 250px);
            height: 100vh;
            background: @layer0;
            opacity: 0;
            transition-duration: @animateSpeed;
            position: fixed;
            pointer-events: none;
            top: 0px;
            left: 0px;
        }

        &.open {
            left: 0px;
            &:after {
                opacity: 0.7;
                pointer-events: initial;
                left: 250px;
            }
        }
    }
</style>