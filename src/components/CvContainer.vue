<template>
    <div class="cv-container">
        <p>cv area</p>

        <Header
            :name="cvDatas[0].name"
            :jobTitle="cvDatas[0].jobTitle"
            :phoneNumber="cvDatas[0].phoneNumber"
        />
        <div class="cv-container-main-top">
            <div class="cv-container-main-top-experiences-area">
                <Experiences :cvDatas="cvDatas" />
            </div>
            <div class="cv-container-main-top-about-area">
                <About :about="cvDatas[0].describe" />
            </div>
        </div>

        <div class="cv-container-main-bottom">
            <div class="cv-container-main-bottom-education-area">
                <Education
                    :highschool="cvDatas[0].highschool"
                    :university="cvDatas[0].university"
                    :department="cvDatas[0].department"
                    :highschoolYear="cvDatas[0].highschoolYear"
                    :universityYear="cvDatas[0].highschoolYear"
                />
            </div>
            <div class="cv-container-main-bottom-about-area">
                <About :about="cvDatas[0].describe" />
            </div>
        </div>

        <br />
        <br />
        <br />
        <pre>
            {{ cvDatas }}
        </pre>
    </div>
</template>

<script>
// @ is an alias to /src
import { Header, Experiences, About, Education } from './subcomponents'

export default {
    components: { Header, Experiences, About, Education },
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
    margin: 32px;
    width: 80%;
    border: 1px solid #dadada;
    max-height: 100vh;
    overflow: scroll;

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
            &-about-area {
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
