<template>
    <div class="App">
        <div class="body">
            <div class="content">
                <RouterView />
                <NavBar :popoutNav="$refs.PopoutNav" :links="[
                    {
                        title: 'Home',
                        href: '/'
                    },
                    {
                        title: 'Download',
                        href: '/download'
                    },
                    {
                        title: 'GitHub',
                        href: '/github'
                    },
                    {
                        title: 'About',
                        href: '/about'
                    }
                ]" />
            </div>

            <div class="footer">

            </div>
        </div>

        <PopoutNav ref="PopoutNav" />
    </div>
</template>

<script lang="typescript">
    import NavBar from "./components/NavBar.vue";
    import PopoutNav from "./components/PopoutNav.vue";

    export default {
        components: {
            NavBar,
            PopoutNav
        }
    }
</script>

<style lang="less">
    @import "./assets/scheme.less";

    body {
        margin: 0px;
        padding: 0px;
        background: @layer1;
        overflow: none;
    }
    * {
        box-sizing: border-box;
    }

    .body {
        max-height: 100vh;
        min-height: 100vh;
        width: 100vw;
        overflow-y: auto;

        & > .content {
            min-height: 200vh;
            width: 100%;
        }
    }
</style>