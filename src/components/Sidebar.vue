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
                    :defaultValue="data.defaultValue"
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
                            key: 'name',
                            class: '',
                        },
                        {
                            type: 'text',
                            placeholder: 'Job Title',
                            key: 'jobTitle',
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
                            defaultValue:
                                "I have graduated from Computer Engineering in 2021. In the past, my friend and I founded our small company on software, graphic design and server management in 2014. In this journey, which we started as two partners, we have provided services to more than 300 customers in different areas such as server management and support, web software, web design, graphic design, WordPress and opencart solutions, AdWords configurations and management, and eCommerce solutions. In this way, I have focused on my business in my free time during my university years and progressed on top of what I have learned. Right now, I'm working as a software developer.",
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
                            defaultValue: 'Hepsiburada',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 1 Title',
                            key: 'experience_1_title',
                            class: '',
                            defaultValue: 'Mid Frontend Developer',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 1 Year',
                            key: 'experience_1_year',
                            class: '',
                            defaultValue: '2022 March - Present',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 1 Description',
                            key: 'experience_1_description',
                            class: '',
                            defaultValue:
                                "Hepsiburada is one of the best e-commerce company in Turkey. I'm working as a frontend developer in HepsiAds team. Microfrontends with Single-spa, React & Vue JS -Development of the new UI screens and enhancements to the existing screens.",
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2',
                            key: 'experience_2',
                            class: '',
                            defaultValue: 'SEDBIM',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2 Title',
                            key: 'experience_2_title',
                            class: '',
                            defaultValue: 'Frontend Developer',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2 Year',
                            key: 'experience_2_year',
                            class: '',
                            defaultValue: '2021 July - 2022 March',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 2 Description',
                            key: 'experience_2_description',
                            class: '',
                            defaultValue:
                                'Transport management systems, airport-hotel booking systems, travel agency management systems, B2B. I work in the front-end development of theese projects.',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3',
                            key: 'experience_3',
                            class: '',
                            defaultValue: 'TRNET',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3 Title',
                            key: 'experience_3_title',
                            class: '',
                            defaultValue: 'Intern',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3 Year',
                            key: 'experience_3_year',
                            class: '',
                            defaultValue: '2020 July - 2020 August',
                        },
                        {
                            type: 'text',
                            placeholder: 'Experience 3 Description',
                            key: 'experience_3_description',
                            class: '',
                            defaultValue:
                                'In my 30-day internship, I took part in eCommerce web page creation, AdWords configurations and management, corporate web design, coding the designs and QR Code systems.',
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
