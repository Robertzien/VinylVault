<template>
	<li class="album">
		<img class="album__image" :src="coverImage" alt="" />
		<h3 class="album__title">{{ title }}</h3>
		<h5 class="album__year">{{ year }}</h5>
		<h5 class="album__genre">{{ genre }}</h5>
	</li>
</template>

<script>
export default {
	props: {
		title: String,
		year: String,
		genre: String,
		coverImage: String,
	},
};
</script>

<style scoped>
.album {
	margin-bottom: 1rem;
	text-align: center;
	background: #1e1e1e;
	padding-bottom: 1.75rem;
	padding-top: 2rem;
	border-radius: .5rem;
	box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
	margin: 0;
}

.album:hover {
	background-color: #df803223;
	cursor: pointer;
	transition: 0.15s ease-in-out;
}

.album__image {
	width: 200px;
	height: 200px;
	margin-bottom: 1rem;
	box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
	border-radius: 0.25rem;
}

.album__image::before {
	content: "";
	width: 200px;
	height: 200px;
	background: black;
}

.album__title {
	margin-top: 0.75rem;
	margin-bottom: 0.5rem;
}

.album__year {
	margin: 0;
	margin-bottom: 1rem;
}

.album__genre {
	color: grey;
	font-weight: 200;
}
</style>
