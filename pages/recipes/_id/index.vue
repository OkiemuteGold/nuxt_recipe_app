<template>
    <section class="single_recipe">
        <h1>{{ recipe.title }}</h1>

        <div
            class="single_recipe_bg"
            :style="{ backgroundImage: `url(${recipe.thumbnail})` }"
        >
            <!-- <img :src="recipe.thumbnail" :alt="recipe.title" /> -->
        </div>

        <p>{{ recipe.descriptionText }}</p>
    </section>
</template>

<script>
export default {
    asyncData(context) {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: 1,
                            thumbnail: "../images/food1.jpg",
                            title: "Some Food",
                            previewText: "Variety of good food",
                            descriptionText: "This is a delicious meal",
                        },
                        {
                            id: 2,
                            thumbnail: "../images/food2.jpg",
                            title: "Pineapple-baked Salmon",
                            previewText: "Delicious pineapple-baked salmon",
                            descriptionText:
                                "This is a delicious pineapple-baked salmon",
                        },
                        {
                            id: 3,
                            thumbnail: "../images/food3.jpg",
                            title: "Pizza",
                            previewText: "A delicious pizza",
                            descriptionText:
                                "This is some sort of delicious pizza",
                        },
                    ].find((el) => el.id == context.params.id),
                });
            }, 1300);
        });
    },
};
</script>

<style scoped>
.single_recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    text-align: center;
    max-width: 850px;
    margin: auto;
    padding: 30px;
}

.single_recipe h1 {
    text-transform: uppercase;
}

.single_recipe_bg {
    height: 250px;
    background-position: center;
    background-size: 65%;
    background-repeat: no-repeat;
}

p {
    margin-top: 20px;
}
</style>