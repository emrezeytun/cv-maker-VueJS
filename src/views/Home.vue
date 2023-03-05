<template>
    <div class="home">
        <Sidebar @cvDatasChanged="cvDatasChanged" />

        <CvContainer :cvDatas="cvDatas" />
    </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from '@/components/Sidebar.vue'
import CvContainer from '@/components/CvContainer.vue'
import { dummyDatas } from '@/assets/dummyDatas'

export default {
    name: 'Home',
    components: { Sidebar, CvContainer },
    data() {
        return {
            cvDatas: dummyDatas,
        }
    },

    methods: {
        cvDatasChanged(datas) {
            this.cvDatas = datas
        },
    },
}
</script>

<style lang="scss" scoped>
.home {
    display: flex;
}

.sidebar {
    width: 20%;
    max-width: 20%;
}

.cv-container {
    width: 80%;
}
</style>
