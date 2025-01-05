<template>
    <div>
        <h2>This is slot</h2>
        <div>This is def</div>
        <slot></slot>
        <slot name="meat"></slot>
        <slot name="robot"></slot>
        <h6>Next a wood</h6>
        <slot name="wood"></slot>
        <slot name="car" carName="Boogaty"></slot>

        <slot name="main" v-bind="{var1:'myVar1'}"></slot>
    </div>
</template>


<script setup>

</script>