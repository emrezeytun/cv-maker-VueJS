<template>
    <div class="cv-container">
        <p>cv area</p>

        <div class="cv-container-header">
            <h2 class="font-weight">Emre Zeytun</h2>
            <hr />
            <p class="title">Mid Frontend Developer</p>
        </div>

        <Experiences :cvDatas="cvDatas" />

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
import { Experiences } from './subcomponents'

export default {
    components: { Experiences },
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

    .font-weight {
        font-weight: 800;
    }

    &-header {
        background: var(--sidebarColor);
        padding: 24px;
        color: #fff;
        h2 {
            font-size: 34px;
            margin: 0;
        }
    }
}
</style>
