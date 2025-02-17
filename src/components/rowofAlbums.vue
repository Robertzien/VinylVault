<template>
	<div v-if="albums.length">
		<ul class="albums">
			<SingleAlbum
				v-for="album in albums.slice(0, 5)"
				:key="album.id"
				:title="album.title"
				:year="album.year"
				:genre="album.genre"
				:cover-image="album.cover_image" />
		</ul>
	</div>
</template>

<script>
import SingleAlbum from "./singleAlbum.vue";

export default {
	components: {
		SingleAlbum,
	},
	props: {
		albums: {
			type: Array,
			required: true,
		},
	},
};
</script>

<style scoped>
.albums {
	display: grid;
	grid-template-columns: repeat(5, minmax(150px, 1fr));
	padding: 0;
	margin: 0 auto;
	gap: 1.5rem;
	max-width: 1400px;
}
</style>
