<template>
    <div>
        <div class="tabs">
            <ul>
                <li v-for="tab in tabs" :class="{ 'is-active': tab.isActive }">
                    <a :href="tab.href" @click="selectTab(tab)">{{ tab.name }}</a>
                </li>
            </ul>
        </div>

        <div class="tabs-details">
            <slot></slot>
        </div>
    </div>
</template>

<script>
    export default {
        name: "tabs",
        data() {
            return {
                tabs: []
            };
        },

        created() {

            this.tabs = this.$children;

        },
        methods: {
            selectTab(selectedTab) {
                this.tabs.forEach(tab => {
                    tab.isActive = (tab.name == selectedTab.name);
                });
            }
        }
    }
</script>

<style scoped>
    .tabs ul{
        list-style-type: none;
        padding-left: 0;
        display: flex;
        flex-wrap: wrap;
    }
    .tabs ul li {
        margin-right: 50px;
    }
    .tabs ul li a{
        font-weight: 500;
        font-size: 18px;
        line-height: 20px;
        color: #BABABA;
        text-decoration: none;
    }
    .tabs ul li:last-child{
        margin-right: 0;
    }
    .tabs .is-active a{
        color: #000000;
        border-bottom: 3px solid #2562FE;
        padding-bottom: 10px;
    }
    @media (max-width: 1370px) {
        .tabs ul li {
            margin-right: 30px;
        }
    }
    @media (max-width: 1250px) {
        .tabs ul li {
            margin-bottom: 30px;
        }
    }
</style>