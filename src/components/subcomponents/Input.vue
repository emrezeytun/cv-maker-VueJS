<template>
    <div class="input-container">
        <label :for="keyName">{{ label }}</label>
        <input
            v-if="type === 'text'"
            :type="type"
            :class="className"
            :placeholder="label"
            :key="keyName"
            :value="defaultValue"
            @input="(e) => $emit('onInputChange', keyName, e.target.value)"
        />
        <textarea
            v-else-if="type === 'textarea'"
            :class="className"
            :placeholder="label"
            :rows="rows"
            :cols="columns"
            :value="defaultValue"
            @input="(e) => $emit('onInputChange', keyName, e.target.value)"
        >
        </textarea>
    </div>
</template>

<script>
export default {
    props: {
        type: {
            type: String,
            default: 'text',
        },
        className: {
            type: String,
            default: '',
        },
        label: {
            type: String,
            default: '',
        },
        keyName: {
            type: String,
            default: '',
        },
        defaultValue: {
            type: String,
            default: '',
        },
        columns: {
            type: Number,
            default: 4,
        },
        rows: {
            type: Number,
            default: 50,
        },
    },
}
</script>

<style lang="scss" scoped>
.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 8px;
    label {
        margin-left: 4px;
        color: #fff;
        font-size: 12px;
    }
    input,
    textarea {
        padding: 15px;
        border: 1px solid #ccc;
        border-radius: 3px;
        margin-bottom: 10px;
        font-family: Arial, Helvetica, sans-serif;
        box-sizing: border-box;
        color: #2c3e50;
        font-size: 13px;
        width: 100%;
    }
    input:focus,
    textarea:focus {
        background-color: #fff;
        outline: none;
    }
}
</style>
