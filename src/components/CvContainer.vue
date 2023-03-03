<template>
    <div class="cv-container">
        <p>cv area</p>
        <pre>
            {{ cvDatas }}
        </pre>
    </div>
</template>

<script>
// @ is an alias to /src

export default {
    components: {},
    props: {
        cvDatas: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.cv-container {
    width: 80%;
}
</style>
