<template>
    <div id="cvContainer" class="cv-container">
        <Header
            :name="cvDatas[0].name"
            :jobTitle="cvDatas[0].jobTitle"
            :phoneNumber="cvDatas[0].phoneNumber"
            :bgColor="bgColor"
            :email="cvDatas[0].email"
        />
        <div class="cv-container-main-top">
            <div class="cv-container-main-top-experiences-area">
                <Experiences
                    :experiences="getExperiences"
                    :bgColor="bgColor"
                    :cvDatas="cvDatas"
                />
            </div>
            <div class="cv-container-main-top-about-area">
                <About :bgColor="bgColor" :about="cvDatas[0].describe" />
            </div>
        </div>

        <div class="cv-container-main-bottom">
            <div class="cv-container-main-bottom-education-area">
                <Education
                    :highschool="cvDatas[0].highschool"
                    :university="cvDatas[0].university"
                    :department="cvDatas[0].department"
                    :highschoolYear="cvDatas[0].highschoolYear"
                    :universityYear="cvDatas[0].universityYear"
                    :bgColor="bgColor"
                />
            </div>
            <div class="cv-container-main-bottom-skills-area">
                <Skills
                    :skills="[
                        cvDatas[0].skill1,
                        cvDatas[0].skill2,
                        cvDatas[0].skill3,
                        cvDatas[0].skill4,
                        cvDatas[0].skill5,
                        cvDatas[0].skill6,
                    ]"
                    :bgColor="bgColor"
                />
            </div>
        </div>
    </div>
</template>

<script>
// @ is an alias to /src
import { Header, Experiences, About, Education, Skills } from './subcomponents'

export default {
    components: { Header, Experiences, About, Education, Skills },
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
    methods: {
        getBgColor(color) {
            return `background-color: ${color}`
        },
    },
    computed: {
        getExperiences() {
            return [
                {
                    name: this.cvDatas[0].experience_1,
                    year: this.cvDatas[0].experience_1_year,
                    title: this.cvDatas[0].experience_1_title,
                    description: this.cvDatas[0].experience_1_description,
                },
                {
                    name: this.cvDatas[0].experience_2,
                    year: this.cvDatas[0].experience_2_year,
                    title: this.cvDatas[0].experience_2_title,
                    description: this.cvDatas[0].experience_2_description,
                },
                {
                    name: this.cvDatas[0].experience_3,
                    year: this.cvDatas[0].experience_3_year,
                    title: this.cvDatas[0].experience_3_title,
                    description: this.cvDatas[0].experience_3_description,
                },
            ]
        },
    },
}
</script>

<style lang="scss" scoped>
.cv-container {
    margin: 64px 32px 32px 32px;
    width: 80%;
    border: 1px solid #dadada;

    &-main {
        &-top {
            display: flex;
            &-experiences-area {
                width: 50%;
            }
            &-about-area {
                width: 50%;
            }
        }
        &-bottom {
            display: flex;
            &-education-area {
                width: 50%;
            }
            &-skills-area {
                width: 50%;
            }
        }
    }

    &-about-area {
        width: 40%;
    }

    .font-weight {
        font-weight: 800;
    }
}
</style>
