<template>
    <div>
        <div class="cv-container-experiences">
            <div :style="getBgColor" class="cv-container-title">
                <p>Experiences</p>
            </div>
            <div
                v-for="(experience, index) in experiences"
                class="cv-container-experiences-item"
                :key="index"
            >
                <div class="cv-container-experiences-item-company">
                    <p class="font-weight">{{ experience.name }}</p>
                    <p class="experience-year">
                        {{ experience.year }}
                    </p>
                </div>
                <p class="experience-title">
                    {{ experience.title }}
                </p>
                <p>
                    {{ experience.description }}
                </p>
                <hr v-if="index !== experiences.length - 1" />
            </div>
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
        experiences: {
            type: Array,
            default: () => [],
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

    hr {
        border: 1px solid rgba(0, 0, 0, 0.07);
    }

    .font-weight {
        font-weight: 800;
    }

    .experience-title {
        font-style: italic;
        font-size: 14px;
        margin-bottom: 12px;
    }
    &-experiences {
        padding: 24px;

        &-item {
            padding: 8px;
            &-company {
                display: flex;
                justify-content: space-between;
            }
        }

        .experience-year {
            margin-left: 24px;
        }
        p {
            margin: 0;
        }
    }
}
</style>
