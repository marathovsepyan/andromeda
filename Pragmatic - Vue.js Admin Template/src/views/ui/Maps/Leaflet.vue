<template>
	<div class="page-leaflet scrollable">
		<div class="page-header">
			<h1>Leaflet</h1>
			<el-breadcrumb separator="/">
				<el-breadcrumb-item :to="{ path: '/' }"><i class="mdi mdi-home-outline"></i></el-breadcrumb-item>
				<el-breadcrumb-item>Components</el-breadcrumb-item>
				<el-breadcrumb-item>Maps</el-breadcrumb-item>
				<el-breadcrumb-item>Leaflet</el-breadcrumb-item>
			</el-breadcrumb>
		</div>

		<div class="card-base card-shadow--medium map-box">
			<l-map :zoom="zoom" :center="center" :options="{dragging: dragging}">
				<l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
				<l-marker :lat-lng="marker"></l-marker>
			</l-map>
		</div>

		<h4><a href="https://github.com/KoRiGaN/Vue2Leaflet" target="_blank"><i class="mdi mdi-link-variant"></i> reference</a></h4>
	</div>
</template>

<script>

export default {
	name: 'LeafletPage',
	data() {
		return {
			zoom:13,
			center: L.latLng(47.413220, -1.219482),
			url:'http://{s}.tile.osm.org/{z}/{x}/{y}.png',
			attribution:'&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
			marker: L.latLng(47.413220, -1.219482),
			innerWidth: 0,
			dragging: true
		}
	},
	methods: {
		setDragging() {
			this.innerWidth = window.innerWidth
			if(window.innerWidth <= 768) 
				this.dragging = false	
			else
				this.dragging = true	
		}
	},
	created() {
		this.setDragging()
		window.addEventListener('resize', this.setDragging);
	},
	beforeDestroy() {
		window.removeEventListener('resize', this.setDragging);
	}
}
</script>

<style lang="scss" scoped>
.page-leaflet {
	.map-box {
		height: 500px;
		width: 100%;
	}
}
</style>

