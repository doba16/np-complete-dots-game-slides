<template>
    <canvas ref="testCanvasRef"></canvas>
</template>

<script setup>
import { DotsGame, TestCircle, GameEngine, DOT_COLOR_RED, DOT_COLOR_BLUE, DOT_COLOR_GREEN, DOT_COLOR_YELLOW, DOT_COLOR_PURPLE, DUMMY_DOT_COLOR } from "@doba16/predictable-dots-game"
import { ref, onMounted } from "vue";
import "./dots.css"

// IMPORTANT: Variable should be named the same as the ref.
const testCanvasRef = ref(null);

const R = DOT_COLOR_RED
const B = DOT_COLOR_BLUE
const G = DOT_COLOR_GREEN
const Y = DOT_COLOR_YELLOW
const P = DOT_COLOR_PURPLE
const D = DUMMY_DOT_COLOR

onMounted(() => {
    console.log("Mein tolles Canvas:", testCanvasRef)

    const engine = new GameEngine(testCanvasRef.value)
    engine.initialize()

    new DotsGame({
        engine,
        width: 6,
        height: 6,
        allowedMoves: 30,
        dotSequence: [
            G, D, D, D, Y, R,
            Y, B, D, R, R, R,
            P, G, R, D, Y, R,
            Y, P, R, B, B, Y,
            P, Y, P, G, P, G,
            G, Y, G, P, G, Y,

            Y, B, G, G, Y, D, B, P, G,
            Y, D, Y, B, B
        ],
        afterSequenceEnds: "dummy"
    })
});

</script>