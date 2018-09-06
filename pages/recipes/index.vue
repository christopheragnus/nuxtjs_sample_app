<template>
    <section class="recipes">
        <Recipe 
          v-for="recipe in recipes" 
          :key='recipe.id'
          :thumbnail="recipe.thumbnail"
          :title="recipe.title"
          :previewText="recipe.previewText"
          :id="recipe.id" />
        
    </section>
</template>

<script> 
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData() {
      return new Promise((resolve, request) => {
          setTimeout(() => {
              resolve({
                  recipes: [
                    {
                      id: "1",
                      title: "Delicious Pizza",
                      previewText: "Awesome Pizza",
                      thumbnail: "https://img.buzzfeed.com/thumbnailer-prod-us-east-1/video-api/assets/117944.jpg",
                    },
                    {
                      id: "2",
                      title: "Sea Foood",
                      previewText: "Sushi",
                      thumbnail: "https://www.ennri.com/images/slides/slide_05.png",
                    }]
              })
          }, 1500 )
      })
    }
};
</script>

<style scoped>
.recipes {
    display:flex;
    flex-flow:row wrap;
    justify-content: center;
    align-items: center;
}

.recipe {
    box-sizing: border-box;
    width: 280px;
    padding: 8px;
    border: 1px solid #ccc;
    box-shadow: 0 2px 2px #aaa;
    margin: 10px;
}

.thumbnail {
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 200px;
}

</style>