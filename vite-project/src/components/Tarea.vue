<script setup>
const props = defineProps({
    name: {
        type:String,
        default: 'NaN'


    },
    index:{
        type:Number
    }
})

const emit = defineEmits([
    'emitTarea'
])

const erase =(index) =>{
    console.log('borrar',index)
    emit('emitTarea', index)    
}
</script>

<template>
    <div class="flex justify-between px-4 py-2 bg-red-600 rounded">
        {{ props.name }}
        <span class="inline-block px-2 text-white bg-red-400 rounded hover:cursor-pointer" @click="erase(props.index)">
            X
        </span>
    </div>

    
</template>

<style scoped>
</style>