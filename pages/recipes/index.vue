<template>
  <section class="recipes">
    <Recipe 
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
  components: {
    Recipe
  },
  asyncData() {
    // could use axios or ajax call here
    // return axios.get()
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Delicious food",
              previewText: "lksjdf;lajsdflkjasdfl;kajsf",
              thumbnail: "https://cookieandkate.com/images/2020/04/black-bean-tacos-recipe-2-550x824.jpg"
            },
            {
              id: "2",
              title: "Fantastic meal",
              previewText: "alsjdfklasjhdf;ajshdfklasjdhfjjdfhsk",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
            }
          ]
        })
      }, 1500)
    })
  }
}
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-content: center;
}



</style>