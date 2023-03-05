<template>
    <div :style="getBgColor" class="header">
        <div class="header-information">
            <h2 class="font-weight">{{ name }}</h2>
            <h2 class="header-information-mail">{{ email }}</h2>
        </div>
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
        name: {
            type: String,
            default: '',
        },
        email: {
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
    &-information {
        display: flex;
        justify-content: space-between;
        align-items: center;
        &-mail {
            font-size: 16px !important;
            font-weight: 400;
        }
    }
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
