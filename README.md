# Micro-bit-lightsensor-Atchya-and-cynthia



let reading = 0
let level_of_light = 0
let item = 0
input.onButtonPressed(Button.A, function () {
    music.rest(music.beat(BeatFraction.Sixteenth))
    level_of_light = input.lightLevel()
    led.plot(0, 0)
    basic.showLeds(`
        . . . . .
        . . . . .
        # # # # #
        . . . . .
        . . . . .
        `)
    if (level_of_light < 25) {
        music.ringTone(262)
    } else if (level_of_light < 50) {
        music.ringTone(294)
    } else if (level_of_light < 100) {
        music.ringTone(330)
    } else if (level_of_light < 125) {
        music.ringTone(349)
    } else if (level_of_light < 200) {
        music.ringTone(392)
    } else {
        music.ringTone(440)
    }
})
basic.forever(function () {
    item = input.lightLevel()
    led.plotBarGraph(
        reading,
        10
    )
})
