<template>
	<vue-scroll class="page-dashboard">

        <tabs>
            <tab :name="translate('Dashboard')" :selected="true">
                <dashboard />
            </tab>
            <tab :name="translate('Screenshot')">
                <h1>{{translate('Screenshot')}}</h1>
            </tab>
            <tab :name="translate('Automation')">
                <h1>{{translate('Automation')}}</h1>
            </tab>
            <tab :name="translate('ShellConsole')" >
                <h1>{{translate('ShellConsole')}}</h1>
            </tab>
            <tab :name="translate('CodingConsole')">
                <h1>{{translate('CodingConsole')}}</h1>
            </tab>
            <tab :name="translate('DebugConsole')">
                <h1>{{translate('DebugConsole')}}</h1>
            </tab>
            <tab :name="translate('VPN')">
                <h1>{{translate('VPN')}}</h1>
            </tab>
        </tabs>
	
	</vue-scroll>
</template>

<script>
    import tabs from "../../components/main_components/tabs";
    import tab from "../../components/main_components/tab";
    import Dashboard from "./DashboardTab/index";


export default {
	name: 'Dashboard',
    components: {
        tabs,tab,
        'dashboard':Dashboard
	},
	data () {
		return {}
	},
	computed: {},
	methods: {},
	mounted() {},
	beforeDestroy() {},

}
</script>

<style lang="scss" scoped>
@import '../../assets/scss/_variables';

</style>

<style lang="scss">
.page-dashboard {}

@media (max-width: 768px) {
	.page-dashboard {
		.vb-content {
			padding: 0 5px !important;
			margin: -5px;
			width: calc(100% + 10px) !important;
		}
	}
}
</style>


