<template>
    <div class="header">
        <h2 class="font-weight">{{ name }}</h2>
        <hr />
        <div class="header-description">
            <p class="title">{{ jobTitle }}</p>
            <p class="phone">{{ phoneNumber }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        cvDatas: {
            type: Array,
            default: () => [],
        },
        name: {
            type: String,
            default: '',
        },
        jobTitle: {
            type: String,
            default: '',
        },
        phoneNumber: {
            type: String,
            default: '',
        },
        bgColor: {
            type: String,
            default: '#ff4c4c',
        },
    },
    computed: {
        getBgColor() {
            return `background-color: ${this.bgColor};`
        },
    },
}
</script>

<style lang="scss" scoped>
.header {
    background: var(--sidebarColor);
    padding: 24px;
    color: #fff;
    &-description {
        display: flex;
        justify-content: space-between;
    }
    h2 {
        font-size: 34px;
        margin: 0;
    }
    hr {
        border: 1px solid rgba(0, 0, 0, 0.09);
    }
}
</style>
