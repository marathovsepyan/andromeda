<template>
    <div class="container-fluid">
        <div class="row">
            <phone-select-style class="col-lg-4"/>
            <navigation class="col-lg-8" />
        </div>
    </div>
</template>

<script>
    import PhoneSelectStyle from "../PhoneSelectStyle/PhoneSelectStyle";
    import Navigation from "./Navigation";
    export default {
        name: "Dashboard",
        components: {
             Navigation,
            PhoneSelectStyle
        },
    }
</script>

<style scoped>

</style>