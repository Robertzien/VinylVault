<template>
	<div class="container container--heading">
		<h2 class="heading__title">{{ title }}</h2>
		<a v-if="linkText && linkUrl" class="heading__link" :href="linkUrl">{{ linkText }} ></a>
	</div>
</template>

<script>
export default {
	props: {
		title: {
			type: String,
			required: true,
		},
		linkText: {
			type: String,
			default: "",
		},
		linkUrl: {
			type: String,
			default: "#",
		},
	},
};
</script>

<style scoped>
.heading__title {
	margin-right: 1rem;
	color: #df8032;
}

.heading__link {
	font-size: 14px;
	text-decoration: none;
	margin: 0;
	font-weight: 200;
	margin-bottom: 0.2rem;
}
</style>
