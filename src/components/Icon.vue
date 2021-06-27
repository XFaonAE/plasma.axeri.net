<template>
    <i :class=" 'ms-Icon ' + 'ms-Icon--' + icon "></i>
</template>

<script lang="ts">
    export default {
        props: [ "icon" ]
    }
</script>