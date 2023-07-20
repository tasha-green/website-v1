<template>
    <div class="page-loader" v-if="!isLoaded">
        <p>Loading...</p>
    </div>

</template>

<script>
    export default {
        data: () => {
            return {
                isLoaded: false
            }
        },
        mounted() {
            document.onreadystatechange = () => {
                if(document.readyState == "complete") {
                    setTimeout(() => {
                        this.isLoaded = true;
                    }, 1000)
                }
            }
        }
    }
</script>

<style scoped>
    .page-loader {
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background-color: antiquewhite;
        z-index: 999;
    }
</style>