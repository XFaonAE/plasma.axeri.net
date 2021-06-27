<template>
    <div class="PopoutNav">

    </div>
</template>

<style lang="less">
    @import "../assets/scheme.less";

    .PopoutNav {
        width: 250px;
        height: 100vh;
        background: @layer2;
        display: flex;
        position: fixed;
        top: 0px;
        left: -250px;
        transition-duration: @animateSpeed;

        &.open {
            left: 0px;
        }
    }
</style>