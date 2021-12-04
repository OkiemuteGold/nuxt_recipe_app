<template>
    <nuxt-link :to="`/recipes/${id}`">
        <article class="recipe">
            <div
                class="thumbnail"
                :style="{ backgroundImage: `url(${thumbnail})` }"
            ></div>

            <h1>{{ title }}</h1>
            <p>{{ previewText }}</p>
        </article>
    </nuxt-link>
</template>

<script>
export default {
    props: ["thumbnail", "title", "previewText", "id"],
};
</script>

<style scoped>
a {
    text-decoration: none;
    color: #121212;
}
.recipe {
    box-sizing: border-box;
    width: 280px;
    padding: 8px 8px 12px;
    margin: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-shadow: 0 2px 2px #aaa;
}

.thumbnail {
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 200px;
}

h1 {
    margin-top: 5px;
}

p {
    margin-bottom: 0;
}
</style>