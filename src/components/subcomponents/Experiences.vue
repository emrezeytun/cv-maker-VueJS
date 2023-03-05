<template>
    <div>
        <div class="cv-container-experiences">
            <div class="cv-container-title"><p>Experiences</p></div>
            <div class="cv-container-experiences-item">
                <div class="cv-container-experiences-item-company">
                    <p class="font-weight">{{ cvDatas[0].experience_1 }}</p>
                    <p class="experience-year">
                        {{ cvDatas[0].experience_1_year }}
                    </p>
                </div>
                <p class="experience-title">
                    {{ cvDatas[0].experience_1_title }}
                </p>
                <p>
                    {{ cvDatas[0].experience_1_description }}
                </p>
            </div>

            <hr />

            <div class="cv-container-experiences-item">
                <div class="cv-container-experiences-item-company">
                    <p class="font-weight">{{ cvDatas[0].experience_2 }}</p>
                    <p class="experience-year">
                        {{ cvDatas[0].experience_2_year }}
                    </p>
                </div>
                <p class="experience-title">
                    {{ cvDatas[0].experience_2_title }}
                </p>
                <p>
                    {{ cvDatas[0].experience_2_description }}
                </p>
            </div>

            <hr />

            <div class="cv-container-experiences-item">
                <div class="cv-container-experiences-item-company">
                    <p class="font-weight">{{ cvDatas[0].experience_3 }}</p>
                    <p class="experience-year">
                        {{ cvDatas[0].experience_3_year }}
                    </p>
                </div>
                <p class="experience-title">
                    {{ cvDatas[0].experience_3_title }}
                </p>
                <p>
                    {{ cvDatas[0].experience_3_description }}
                </p>
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
