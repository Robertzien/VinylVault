<template>
	<div id="app">
		<div class="navbar">
			<NavBar />
		</div>
		<div class="hero">
			<Hero />
		</div>
		<div class="section-heading">
			<SectionHeading title="De nieuwste LP's" linkText="Bekijk alle nieuwe LP's" linkUrl="#" />
		</div>
		<div class="row-of-albums">
			<RowOfAlbums :albums="albums" />
		</div>
	</div>
</template>

<script>
import axios from "axios";
import RowOfAlbums from "./components/sections/rowOfAlbums.vue";
import SectionHeading from "./components/sections/sectionHeading.vue";
import NavBar from "./components/main/nav.vue";
import Hero from "./components/main/hero.vue";
import './assets/styles.css'

export default {
	components: {
		RowOfAlbums,
		SectionHeading,
		NavBar,
		Hero,
	},
	data() {
		return {
			albums: [],
		};
	},
	created() {
		this.fetchAlbums();
	},
	methods: {
		async fetchAlbums() {
			try {
				const response = await axios.get("https://api.discogs.com/database/search", {
					params: {
						q: "LP",
						type: "release",
						token: "FbAevpWuLulcMOJpLqTmUMPGyQngGwxLlIRPZVfN",
					},
				});
				this.albums = response.data.results;
			} catch (error) {
				console.error("Fout bij het ophalen van data:", error);
			}
		},
	},
};
</script>
