<template>
    <div class="sidebar">
        <!-- eslint-disable-next-line vue/require-v-for-key -->
        <div v-for="sidebarData in sidebarDatas">
            <h1>{{ sidebarData.name }}</h1>
            <!-- eslint-disable-next-line vue/require-v-for-key -->
            <div v-for="data in sidebarData.datas" class="sidebar-input">
                <Input
                    :type="data.type"
                    :placeholder="data.placeholder"
                    :keyName="data.key"
                    :class="data.class"
                    :label="data.placeholder"
                    :rows="data.rows"
                    :columns="data.columns"
                    @onInputChange="onInputChange"
                />
            </div>
        </div>
    </div>
</template>

<script>
import Input from '@/components/subcomponents/Input.vue'

export default {
    name: 'SideBar',
    data() {
        return {
            sidebarDatas: [
                {
                    name: 'Personal Information',
                    datas: [
                        {
                            type: 'text',
                            placeholder: 'Name',
                            key: 'Name',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Address',
                            key: 'address',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Phone Number',
                            key: 'phoneNumber',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'E-Mail',
                            key: 'email',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'LinkedIn Profile',
                            key: 'linkedin',
                            class: '',
                        },
                        {
                            type: 'textarea',
                            placeholder: 'Describe Yourself',
                            key: 'describe',
                            class: '',
                            rows: 4,
                            columns: 100,
                        },
                    ],
                },
                {
                    name: 'Education',
                    datas: [
                        {
                            type: 'text',
                            placeholder: 'High School',
                            key: 'highschool',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'University',
                            key: 'university',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Department',
                            key: 'department',
                            class: '',
                        },
                    ],
                },
                {
                    name: 'Experiences',
                    datas: [
                        {
                            type: 'text',
                            placeholder: 'Experience 1',
                            key: 'experience_1',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 1 Description',
                            key: 'experience_1_description',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2',
                            key: 'experience_2',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2 Description',
                            key: 'experience_2_description',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3',
                            key: 'experience_3',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3 Description',
                            key: 'experience_3_description',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 4',
                            key: 'experience_4',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 4 Description',
                            key: 'experience_4_description',
                            class: '',
                        },
                    ],
                },
            ],
            cvDatas: [{}],
        }
    },
    components: { Input },
    methods: {
        onInputChange(key, value) {
            this.cvDatas = this.cvDatas.map((data) => {
                return {
                    ...data,
                    [key]: value,
                }
            })
            this.$emit(
                'cvDatasChanged',
                JSON.parse(JSON.stringify(this.cvDatas))
            )
        },
    },
}
</script>

<style lang="scss" scoped>
.sidebar {
    width: 20%;
    max-width: 20%;
    background-color: var(--sidebarColor);
    padding: 16px;
    h1 {
        color: #fff;
        font-size: 16px;
    }
}
</style>
