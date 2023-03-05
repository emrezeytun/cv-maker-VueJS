<template>
    <div class="cv-container">
        <p>cv area</p>

        <Header
            :name="cvDatas[0].name"
            :jobTitle="cvDatas[0].jobTitle"
            :phoneNumber="cvDatas[0].phoneNumber"
        />
        <div class="cv-container-main">
            <div class="cv-container-main-experiences-area">
                <Experiences :cvDatas="cvDatas" />
            </div>
            <div class="cv-container-main-about-area">
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
import { Header, Experiences, About } from './subcomponents'

export default {
    components: { Header, Experiences, About },
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

    &-main {
        display: flex;
        &-experiences-area {
            width: 50%;
        }
        &-about-area {
            width: 50%;
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
