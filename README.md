# Micro-bit-lightsensor-Atchya-and-cynthia

let reading = 0
basic.forever(function () {
    reading = input.lightLevel()
    led.plotBarGraph(
    reading,
    255
    )
})
