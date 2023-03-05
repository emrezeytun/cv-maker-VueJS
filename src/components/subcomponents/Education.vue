<template>
    <div>
        <div class="cv-container-education">
            <div :style="getBgColor" class="cv-container-title">
                <p>Education</p>
            </div>
            <div class="cv-container-education-item">
                <div class="cv-container-education-item-company">
                    <p class="font-weight">{{ highschool }}</p>
                    <p class="experience-year">
                        {{ highschoolYear }}
                    </p>
                </div>
            </div>
            <hr />
            <div class="cv-container-education-item">
                <div class="cv-container-education-item-company">
                    <p class="font-weight">{{ university }}</p>
                    <p class="experience-year">
                        {{ universityYear }}
                    </p>
                </div>
                <p class="title">
                    {{ department }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        highschool: {
            type: String,
            default: '',
        },
        highschoolYear: {
            type: String,
            default: '',
        },
        university: {
            type: String,
            default: '',
        },
        universityYear: {
            type: String,
            default: '',
        },
        department: {
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

    hr {
        border: 1px solid rgba(0, 0, 0, 0.07);
    }

    .font-weight {
        font-weight: 800;
    }

    .title {
        font-style: italic;
        font-size: 14px;
        margin-bottom: 12px;
    }
    &-education {
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
