<template>
    <div class="home">
        <div class="download">
            <button @click="downloadPdf" class="download-btn">
                <img :src="pdfIcon" />Download PDF
            </button>
            <button class="download-btn deactivated">
                <img :src="wordIcon" />Download DOC
            </button>
        </div>
        <div class="colors">
            <div
                v-for="color in colorState.colors"
                :key="color"
                :style="getBgColor(color)"
                class="color"
                @click="setColor(color)"
            ></div>
        </div>
        <Sidebar @cvDatasChanged="cvDatasChanged" />

        <CvContainer :bgColor="colorState.activeColor" :cvDatas="cvDatas" />
    </div>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'
import CvContainer from '@/components/CvContainer.vue'
import { dummyDatas } from '@/assets/dummyDatas'
import { pdfIcon, wordIcon } from '@/assets/iconsData'
import { jsPDF } from 'jspdf'

export default {
    name: 'Home',
    components: { Sidebar, CvContainer },
    data() {
        return {
            cvDatas: dummyDatas,
            colorState: {
                activeColor: '#ff4c4c',
                colors: [
                    '#ff4c4c',
                    '#3F497F',
                    '#4E6E81',
                    '#A7727D',
                    '#5D3891',
                    '#E14D2A',
                ],
            },
            pdfIcon,
            wordIcon,
        }
    },

    methods: {
        cvDatasChanged(datas) {
            this.cvDatas = datas
        },
        getBgColor(color) {
            return `background-color: ${color}`
        },
        setColor(color) {
            this.colorState.activeColor = color
        },
        formatToPdf(html) {
            const cloneHtml = html.cloneNode(true)

            cloneHtml.querySelector(
                '.cv-container-main-top-experiences-area'
            ).style.width = '100%'

            cloneHtml.querySelector(
                '.cv-container-main-top-about-area'
            ).style.width = '100%'

            cloneHtml.querySelector(
                '.cv-container-main-top'
            ).style.flexDirection = 'column'

            cloneHtml.querySelector(
                '.cv-container-main-bottom-education-area'
            ).style.width = '100%'

            cloneHtml.querySelector(
                '.cv-container-main-bottom-skills-area'
            ).style.width = '100%'

            cloneHtml.querySelector(
                '.cv-container-main-bottom'
            ).style.flexDirection = 'column'

            return cloneHtml
        },
        downloadPdf() {
            const doc = new jsPDF()

            const html = this.formatToPdf(
                document.querySelector('#cvContainer')
            )

            doc.html(html, {
                callback: function (doc) {
                    doc.save('sample-cv.pdf')
                },
                x: 15,
                y: 15,
                width: 200,
                windowWidth: 650,
            })
        },
    },
}
</script>

<style lang="scss" scoped>
.home {
    display: flex;
    .download {
        position: absolute;
        left: 24.5vw;
        display: flex;
        &-btn {
            &:hover {
                opacity: 0.8;
            }
            img {
                margin-right: 4px;
                height: 24px;
                width: auto;
            }
            transition: 0.5s;
            border-radius: 12px;
            display: flex;
            align-items: center;
            background: #ff4c4c;
            border: none;
            margin: 0 4px 0 0;
            font-size: 16px;
            font-weight: 400;
            cursor: pointer;
            color: #fff;
            padding: 12px 16px;
        }

        .deactivated {
            opacity: 0.5;
            background: gray;
            cursor: no-drop;
        }
    }
    .colors {
        display: flex;
        position: absolute;
        right: 32px;
        .color {
            width: 50px;
            height: 50px;
            margin: 0 4px;
            cursor: pointer;
            border-radius: 50%;
            background: red;
        }
    }
}

.sidebar {
    width: 20%;
    max-width: 20%;
}

.cv-container {
    width: 80%;
}
</style>
