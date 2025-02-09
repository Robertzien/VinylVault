<template>
    <li class="album">
        <img class="album__image" :src="coverImage" alt="">
        <h3 class="album__title">{{ title }}</h3>
        <h5 class="album__year">{{ year }}</h5>
    </li>
</template>

<script>
export default {
    props: {
        title: String,
        year: String,
        coverImage: String,
    }
};
</script>

<style scoped>
.album {
    margin-bottom: 1rem;
    text-align: center;
    background: #000;
    padding: 3rem;
    border-radius: 1.25rem;
}

.album__image {
    width: 175px;
    height: 175px;
    margin-bottom: 0;
    border-radius: 999rem;
    border: solid .25rem white;
}

.album__title {
    margin-top: .75rem;
}

.album__year {
    margin: 0;
}
</style>
