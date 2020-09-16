<template>
    <el-checkbox>{{title}}</el-checkbox>
</template>

<script>
    export default {
        name: "checkbox",
        props: ['title']
    }
</script>

<style >
    .el-checkbox__inner{
        width: 24px;
        height: 24px;
    }
    .el-checkbox__inner::after {
        height: 14px;
        left: 7px;
        position: absolute;
        top: 1px;
        width: 7px;
    }
</style>