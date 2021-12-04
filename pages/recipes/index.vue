<template>
    <section class="recipes">
        <Recipe
            v-for="recipe in recipes"
            :key="recipe.id"
            :id="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :previewText="recipe.previewText"
        />
    </section>
</template>

<script>
import Recipe from "@/components/Recipe.vue";

export default {
    components: {
        Recipe,
    },

    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: 1,
                            thumbnail: "../images/food1.jpg",
                            title: "Some Food",
                            previewText: "Variety of good food",
                        },
                        {
                            id: 2,
                            thumbnail: "../images/food2.jpg",
                            title: "Pineapple-baked Salmon",
                            previewText: "Delicious pineapple-baked salmon",
                        },
                        {
                            id: 3,
                            thumbnail: "../images/food3.jpg",
                            title: "Pizza",
                            previewText: "A delicious pizza",
                        },
                    ],
                });
            }, 1300);
        });
    },
};
</script>

<style scoped>
.recipes {
    display: flex;
    flex-flow: row wrap;
    -ms-flex-flow: row wrap;
    justify-content: center;
}
</style>>