<template>
  <layout>
      <h1>{{ $page.workout.title }}</h1>
  </layout>
</template>

<page-query>
query{
    workout(id : "2") {
        id
        title
        duration
        image
    }
}
</page-query>

<script>
export default {
    metaInfo() {
        return {
            title: this.$page.workout.title
        }
    }
}
</script>

<style>

</style>