<template>
    <div class="NavBar">
        <div class="logo section">
            <RouterLink to="/">Plasma IDE</RouterLink>
        </div>

        <div class="links section">
            <RouterLink :to="link.href" v-for="link in links">
                {{ link.title }}
            </RouterLink>
        </div>

        <button @click="this.toggle()" class="sidebarButton">
            <Icon icon="CollapseMenu" />
        </button>
    </div>
</template>

<script lang="ts">
    import Icon from "./Icon.vue";

    export default {
        props: [ "links" ],
        components: {
            Icon
        },
        mounted() {
            console.log(this.popoutNav);
        },
        data: () => {
            return {
                opened: false
            };
        },
        methods: {
            toggle() {
                if (this.opened) {
                    this.opened = false;
                    this.close();
                    return;
                }

                this.opened = true;
                this.open();
            },
            close() {
                document.querySelector(".PopoutNav")?.classList.remove("open");
            },
            open() {
                document.querySelector(".PopoutNav")?.classList.add("open");
            }
        }
    }
</script>

<style lang="less">
    @import "../assets/scheme.less";

    .NavBar {
        width: 100%;
        height: 50px;
        background: @layer2;
        display: flex;
        position: sticky;
        top: 0px;
        padding: 0px 20px;
        align-items: center;
        justify-content: space-between;

        .logo a {
            color: @accentColor;
            text-decoration: none;
            letter-spacing: 1px;
            font-size: 13px;
            font-family: @logoFont;
            display: flex;
            white-space: nowrap;
            height: 50px;
            padding: 0px 10px;
            margin-left: -10px;
            align-items: center;
            transition-duration: @animateSpeed;

            &:hover {
                background: @layer3;
            }
        }

        .sidebarButton {
            background: transparent;
            height: 50px;
            border: none;
            padding: 0px 10px;
            margin-right: -10px;
            display: none;
            cursor: pointer;
            color: @contrastColor;
            opacity: 0.6;
            transition-duration: @animateSpeed;

            &:hover {
                opacity: 1;
                background: @layer3;
            }

            @media (max-width: 700px) {
                display: block;
            }
        }

        .links {
            display: flex;
            margin-right: -10px;
            overflow-x: auto;
            margin-left: 50px;
            height: 50px;

            &::-webkit-scrollbar {
                width: 0px;
                height: 0px;
            }

            a {
                font-family: @mainFont;
                text-decoration: none;
                height: 50px;
                padding: 0px 10px;
                display: flex;
                align-items: center;
                transition-duration: @animateSpeed;
                color: @contrastColor;
                font-size: 13px;
                border-bottom: 1px solid transparent;
                padding-top: 1px;
                opacity: 0.6;
                
                &:hover {
                    background: @layer3;
                    opacity: 1;
                }

                &.router-link-active {
                    color: @accentColor;
                    border-color: @accentColor;
                    opacity: 1;
                }
            }

            @media (max-width: 700px) {
                display: none;
            }
        }
    }
</style>