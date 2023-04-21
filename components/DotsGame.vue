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
        allowedMoves: 15,
        dotSequence: [
            R, P, G, P, Y, R,
            Y, B, P, R, R, R,
            P, G, R, P, Y, R,
            Y, P, R, B, B, Y,
            P, B, P, G, P, G,
            G, B, G, P, G, Y,

            Y, B, R, R, Y, R, B, P, G,
            Y, R, Y, B, B,

            R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B, R, G, B

        ],
        afterSequenceEnds: "random",
        goals: [
            {
                color: G,
                neededAmount: 12
            }, {
                color: P,
                neededAmount: 10
            }
        ]
    })
});

</script>