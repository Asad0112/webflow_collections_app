<template>
    <Drawer :is_open="is_open" @close="$emit('close')" >
        <template #content>
            <h5 id="drawer-label"
                class="inline-flex items-center mb-6 text-sm font-semibold text-gray-500 uppercase dark:text-gray-400">New
                Product</h5>
            <button @click="$emit('close')" type="button" data-drawer-dismiss="drawer-create-product-default"
                aria-controls="drawer-create-product-default"
                class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 absolute top-2.5 right-2.5 inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white">
                <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd"
                        d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                        clip-rule="evenodd"></path>
                </svg>
                <span class="sr-only" >Close menu</span>
            </button>
            <Form >
                <template #fields="{ refs }">
                    <TextFeild name="firstname" :ref="(ele:any) => { refs.push(ele) }"></TextFeild>
                    <TextFeild name="lastname" :ref="(ele:any) => { refs.push(ele) }"></TextFeild>
                    <TextFeild name="email" :ref="(ele:any) => { refs.push(ele) }"></TextFeild>
                    <TextFeild name="phone" :ref="(ele:any) => { refs.push(ele) }"></TextFeild>
                    <button @click="test" >test</button>
                </template>
            </Form>
           
        </template>
    </Drawer>

</template>

<script setup lang="ts">
    import Drawer from '@/components/functional/drawer.vue'
    import Form from "./form.vue"
    import TextFeild from "./fields/text.vue"
    const props = defineProps({
        is_open: { type: Boolean, default: false }
    })
    
    const test = () => {

    }
</script>