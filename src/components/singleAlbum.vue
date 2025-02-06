<template>
    <li class="album">
        <img class="album__image" :src="coverImage" alt="">
        <h3 class="album__title">{{ title }}</h3>
    </li>
</template>

<script>
export default {
    props: {
        title: String,
        coverImage: String
    }
};
</script>

<style scoped>
.album {
    margin-bottom: 1rem;
}

.album__image {
    width: 225px;
    height: 225px;
    margin-bottom: 0;
    border-radius: 999rem;
    border: solid .25rem white;
}

.album__title {
    margin-top: .75rem;
}
</style>
