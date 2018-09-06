<template>
    <section class="single-recipe">
        <h1> {{ recipe.title }} </h1>
        <div> 
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p> The recipe description. </p>
    </section>
</template>

<script>
export default {
    asyncData(context) {
      return new Promise((resolve, request) => {
          setTimeout(() => {
              resolve({
                  recipe: [
                    {
                      id: "1",
                      title: "Delicious Pizza",
                      previewText: "Awesome Pizza",
                      descriptionText: "This is really delicious",
                      thumbnail: "https://img.buzzfeed.com/thumbnailer-prod-us-east-1/video-api/assets/117944.jpg",
                    },
                    {
                      id: "2",
                      title: "Sea Foood",
                      previewText: "Sushi",
                      descriptionText: "This is really delicious",
                      thumbnail: "https://www.ennri.com/images/slides/slide_05.png",
                    }
                ].find(el => el.id === context.params.id)
              })
          }, 1500 )
      })
    }
}
</script>

<style scoped>
.single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 100%;
}
</style>