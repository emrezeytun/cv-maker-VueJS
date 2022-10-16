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
        />
      </div>
    </div>
  </div>
</template>

<script>
import Input from "@/components/subcomponents/Input.vue";

export default {
  name: "SideBar",
  data() {
    return {
      sidebarDatas: [
        {
          name: "Personal Information",
          datas: [
            { type: "text", placeholder: "Name", key: "Name", class: "" },
            { type: "text", placeholder: "Address", key: "address", class: "" },
            {
              type: "text",
              placeholder: "Phone Number",
              key: "phoneNumber",
              class: "",
            },
            {
              type: "text",
              placeholder: "E-Mail",
              key: "email",
              class: "",
            },
            {
              type: "text",
              placeholder: "LinkedIn Profile",
              key: "linkedin",
              class: "",
            },
            {
              type: "textarea",
              placeholder: "Describe Yourself",
              key: "describe",
              class: "",
              rows: 4,
              columns: 100,
            },
          ],
        },
        {
          name: "Education",
          datas: [
            { type: "text", placeholder: "School", key: "Name", class: "" },
            { type: "text", placeholder: "Address", key: "address", class: "" },
            {
              type: "text",
              placeholder: "Phone Number",
              key: "phoneNumber",
              class: "",
            },
            {
              type: "text",
              placeholder: "E-Mail",
              key: "email",
              class: "",
            },
            {
              type: "text",
              placeholder: "LinkedIn Profile",
              key: "linkedin",
              class: "",
            },
            {
              type: "textarea",
              placeholder: "Describe Yourself",
              key: "describe",
              class: "",
              rows: 4,
              columns: 100,
            },
          ],
        },
      ],
    };
  },
  components: { Input },
};
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
