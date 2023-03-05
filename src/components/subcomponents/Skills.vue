<template>
    <div>
        <div class="cv-container-skills">
            <div :style="getBgColor" class="cv-container-title">
                <p>Skills</p>
            </div>
            <div v-for="(skill, index) in skills" :key="index" class="">
                <div v-if="skill.length" class="cv-container-skills-item">
                    <img :src="skillIcon" />
                    <p class="skill-text">{{ skill }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { skillIcon } from '@/assets/iconsData'
export default {
    data() {
        return {
            skillIcon,
        }
    },
    props: {
        skills: {
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

    .title {
        font-style: italic;
        font-size: 14px;
        margin-bottom: 12px;
    }
    &-skills {
        padding: 24px;

        &-item {
            padding: 8px;
            display: flex;
            img {
                width: 24px;
                height: auto;
            }
            .skill-text {
                margin-left: 8px;
            }
        }

        p {
            margin: 0;
        }
    }
}
</style>
