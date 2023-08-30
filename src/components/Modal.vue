<template>
    <div @click.self="closeModel" class="fixed top-0 w-full h-full bg-blue-500 bg-opacity-80">
        <div class="w-[400px] p-8 my-32 mx-auto bg-blue-700 rounded-xl text-white">
                <slot/>
                <div class="mt-4">
                    <slot name="links"></slot>
                </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ['header', 'text'],
    methods: {
        closeModel() {
            this.$emit('close')
        }
    }
}
</script>
<style></style>