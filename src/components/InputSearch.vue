<script>
export default {
    props: {
        modelValue: { type: String, default: "" }
    },
    emits: ["submit", "update:modelValue"],
    methods: {
        updateModelValue(e) {
            this.$emit("updat:modelValue", e.target.value)
        },
        submit() {
            this.$emit("submit")
        }
    }
}
</script>

<template>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="Nhập thông tin cần tìm" :value="modelValue"
            @input="updateModelValue" @keyup.enter="submit" />
        <div class="input-group-append">
            <button type="button" @click="submit" class="btn btn-outline-secondary">
                <i class="fas fa-search"></i> Tìm kiếm
            </button>
        </div>
    </div>
</template>