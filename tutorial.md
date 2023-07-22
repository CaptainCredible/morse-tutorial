# My Tutorial

## Step 1

Add code to register button presses

```blocks
Morse.whileButtonAisHeld(function () {
    Morse.makeMorseBeep(262)
    Morse.makeMorseBlink()
    radio.sendString("beep")
})
```

## Step 2

Do more stuff

```blocks
basic.showString(":)")
basic.showString(":(")
```

## Step 3

Try it out on your microbit!

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>