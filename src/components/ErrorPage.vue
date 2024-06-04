<template>
    <div class="error-page">
        <h1>Oops! Something went wrong.</h1>
        <h3>The page you are looking does not exist</h3>
        <p>Go back to <router-link :to="`/`">Home page</router-link></p>
    </div>
</template>

<script>

</script>

<style scoped>
.error-page {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    font-family: Arial, sans-serif;
    text-align: center;
    color: #333;
}
</style>