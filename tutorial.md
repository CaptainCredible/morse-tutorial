# My Tutorial

## Step 1

Legg til klosser for å registrere knappetrykk og lage pipelyder og blinking.
vi må bruke den spesielle "whileButtonAisHeld" klossen for at mikrobiten skal
reagere fort nok på knappetrykkene våre. Husk at du kan trykke på lysbæren for å se hva du skal lage.

```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(880)
    Morse.makeMorseBlink()
})
```

## Step 2

Nå kan vi legge til klossen for å sette radiogruppe. Da kan vi gå videre å sende morse signalene ut over radio!
Bare microbit med samme radiogruppe kan sende og motta morsesignaler med hverandre.
Velg ett eget tall til radiogruppen til deg og de du skal snakke med.
```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
})
radio.setGroup(1)
```

## Step 3

Først kan vi legge til "radio send tekst" klossen for å sende signalene ut til andre micro:bit:

```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(880)
    Morse.makeMorseBlink()
    radio.sendString("beep")
})
radio.setGroup(1)
```

## Step 4

Deretter må vi legge til "når radio mottar (receivedString)" klossen og fortelle micro:biten vår hva den skal gjære når den mottar tekst fra en annen micro:bit på samme radiogruppe

```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
    radio.sendString("beep")
})
radio.onReceivedString(function (receivedString) {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
})
radio.setGroup(1)
```
## Step 5

Da har du en fungerende sender og mottaker. Da kan du sende denne meldingen: ".... ..- .-. .-. .- -.-.--"
Hvis du vil bruke en egen morsenøkkel tilkoblet micro:biten kan du gå videre til neste steg.

```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
    radio.sendString("beep")
})
radio.onReceivedString(function (receivedString) {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
})
radio.setGroup(1)
```

## Step 6

Koble morsenøkkelen din til micro:biten så den ene ledningen går til "GND" og den andre går til "1" og bytt ut "while button A is held" med "while pin P1 is connected to GND". Husk at du må selv velge P1 på klossen istedet for P0

```blocks
Morse.whilePinIsConnectedToGND(DigitalPin.P1, function () {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
    radio.sendString("beep")
})
radio.onReceivedString(function (receivedString) {
    Morse.makeMorseBeep(600)
    Morse.makeMorseBlink()
})
radio.setGroup(1)
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>