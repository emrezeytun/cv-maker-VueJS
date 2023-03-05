<template>
    <div>
        <div class="cv-container-experiences">
            <div class="cv-container-title"><p>Experiences</p></div>
            <div class="cv-container-experiences-item">
                <div class="cv-container-experiences-item-company">
                    <p class="font-weight">Hepsiburada</p>
                    <p class="experience-year">2023-2024</p>
                </div>
                <p class="experience-title">Mid Frontend Developer</p>
                <p>
                    Hepsiburada is one of the best e-commerce company in Turkey.
                    I'm working as a frontend developer in HepsiAds team.
                    Microfrontends with Single-spa, React & Vue JS -Development
                    of the new UI screens and enhancements to the existing
                    screens.
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
        width: 40%;

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
