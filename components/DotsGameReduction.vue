<template>
    <canvas ref="testCanvasRef"></canvas>
</template>

<script setup>
import { DotsGame, GameEngine, DOT_COLOR_RED, DOT_COLOR_BLUE, DOT_COLOR_GREEN, DOT_COLOR_YELLOW, DOT_COLOR_PURPLE, DUMMY_DOT_COLOR } from "@doba16/predictable-dots-game"
import { ref, onMounted } from "vue";
import "./dots.css"

// IMPORTANT: Variable should be named the same as the ref.
const testCanvasRef = ref(null);

const DD = DUMMY_DOT_COLOR

const numColors = 7

const V1 = {
    name: "V1",
    color: `hsl(${360 / numColors * 0 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 0 + 15}deg, 80%, 50%, 70%)`
}

const V2 = {
    name: "V2",
    color: `hsl(${360 / numColors * 1 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 1 + 15}deg, 80%, 50%, 50%)`
}

const V3 = {
    name: "V3",
    color: `hsl(${360 / numColors * 2 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 2 + 15}deg, 80%, 50%, 50%)`
}

const V4 = {
    name: "V4",
    color: `hsl(${360 / numColors * 3 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 3 + 15}deg, 80%, 50%, 50%)`
}

const V5 = {
    name: "V5",
    color: `hsl(${360 / numColors * 4 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 4 + 15}deg, 80%, 50%, 50%)`
}

const AA = {
    name: "AA",
    color: `hsl(${360 / numColors * 5 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 5 + 15}deg, 80%, 50%, 50%)`
}

const BB = {
    name: "BB",
    color: `hsl(${360 / numColors * 6 + 15}deg, 80%, 50%)`,
    shadowColor: `hsla(${360 / numColors * 6 + 15}deg, 80%, 50%, 50%)`
}

onMounted(() => {
    console.log("Mein tolles Canvas:", testCanvasRef)

    const engine = new GameEngine(testCanvasRef.value)
    engine.initialize()

    new DotsGame({
        engine,
        width: 55,
        height: 4,
        allowedMoves: 14,
        dotSequence: [
            DD, AA, DD,   DD, AA, DD,   DD, AA, DD,   DD, AA, DD,   DD, AA, DD, /* */ DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,
            DD, V1, V1,   DD, V2, V2,   DD, V3, V3,   DD, V4, V4,   DD, V5, V5, /* */ DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,  DD, DD, BB, BB, DD,
            DD, V1, V1,   DD, V2, V2,   DD, V3, V3,   DD, V4, V4,   DD, V5, V5, /* */ DD, BB, V1, V2, BB,  DD, BB, V1, V3, BB,  DD, BB, V1, V4, BB,  DD, BB, V2, V3, BB,  DD, BB, V2, V4, BB,  DD, BB, V2, V5, BB,  DD, BB, V3, V4, BB,  DD, BB, V4, V5, BB,
            DD, AA, DD,   DD, AA, DD,   DD, AA, DD,   DD, AA, DD,   DD, AA, DD, /* */ DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,  DD, DD, DD, DD, DD,
        ],
        afterSequenceEnds: "dummy",
        goals: [
            {
                color: AA,
                neededAmount: 8
            }, {
                color: BB,
                neededAmount: 24
            }
        ]
    })
});

</script>