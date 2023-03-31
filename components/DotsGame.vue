<template>
    <canvas ref="testCanvasRef"></canvas>
</template>

<script setup>
import { DotsGame } from "@doba16/predictable-dots-game"
import { ref, onMounted } from "vue";
import "./canvas-style.css"

// IMPORTANT: Variable should be named the same as the ref.
const testCanvasRef = ref(null);

onMounted(() => {
    console.log("Mein tolles Canvas:", testCanvasRef)

    new DotsGame({
        canvas: testCanvasRef.value,
        width: 6,
        height: 6
    }).startDrawing()

    console.log("Started drawing...")
});

</script>