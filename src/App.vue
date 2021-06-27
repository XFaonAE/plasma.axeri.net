<template>
    <div class="App">
        <NavBar :links="[
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

        <div class="body">
            <div class="content">
                <RouterView />
            </div>

            <div class="footer">

            </div>
        </div>
    </div>
</template>

<script lang="typescript">
    import NavBar from "./components/NavBar.vue";

    export default {
        components: {
            NavBar
        }
    }
</script>

<style lang="less">
    @import "./assets/scheme.less";

    body {
        margin: 0px;
        padding: 0px;
        background: @layer1;
    }
    * {
        box-sizing: border-box;
    }
</style>