<template>
    <div>
        <div class="cv-container-about">
            <div :style="getBgColor" class="cv-container-title">
                <p>About</p>
            </div>
            <div class="cv-container-about-item">
                <div class="cv-container-about">
                    <p>
                        {{ about }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        about: {
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
.cv-container {
    &-title {
        background: var(--sidebarColor);
        color: #fff;
        padding: 12px;
        margin-bottom: 12px;
        border-top-left-radius: 12px;
        border-top-right-radius: 12px;
    }

    &-about {
        padding: 24px;

        p {
            margin: 0;
        }
    }
}
</style>
