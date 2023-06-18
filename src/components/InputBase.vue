<template>
    <input :type="type" :value="modelValue" @input="update" :placeholder="placeholder" />
</template>
<script>
export default {

    props: {
        type: String,
        modelValue: [String, Number],
        placeholder: String,
    },

    methods: {
        update(event) {
            this.$emit("update:modelValue", event.target.value)
        },

    }


}
</script>
<style scoped>
input {
    width: 100%;
    border: .1px solid black;
    outline: none;
    height: 30px;
    border-radius: 5px;
    padding: 5px;
}
</style>