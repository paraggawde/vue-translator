<template>
    <h1 class="text-center">{{translatedText}}</h1>
</template>
 <script>
export default {
    name: 'VueTranslate',
    props: ['translatedText']
}
</script>

<style>
h1{
    font-weight: 800;
}
</style>

 