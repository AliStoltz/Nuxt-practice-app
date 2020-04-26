<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{recipe.descriptionText}}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    // could use axios or ajax call here
    // return axios.get()
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious food",
              previewText: "lksjdf;lajsdflkjasdfl;kajsf",
              descriptionText: "thwhjwrkejh slkjhdfaliuhf lksajdf klsa djfhalkshdf lauh flkajhsd fkljasf",
              thumbnail: "https://cookieandkate.com/images/2020/04/black-bean-tacos-recipe-2-550x824.jpg"
            },
            {
              id: "2",
              title: "Fantastic meal",
              previewText: "alsjdfklasjhdf;ajshdfklasjdhfjjdfhsk",
              descriptionText: "thwhjwrkejh slkjhdfaliuhf lksajdf klsa djfhalkshdf lauh flkajhsd fkljasf",
              thumbnail: "https://www.bbcgoodfood.com/sites/default/files/recipe-collections/collection-image/2013/05/chorizo-mozarella-gnocchi-bake-cropped.jpg"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>

<style>
.single-recipe {
  display: flex;
  flex-flow:column;
  justify-content: center;
  align-items: center; 
  text-align: center;
  padding: 30px;
}

.recipe-image {
  width: 100%;
}
</style>