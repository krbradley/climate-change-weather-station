### @activities true

# Climate Change Weather Station Tutorial

## Introduction



## Reading and Recording temperature

### Step 1 - Add code to display temperature.
Click on the ``||basic:Basic||`` category in the Toolbox. 
Drag the ``||basic:show number||`` block into the ``||basic:forever||`` block. 


```blocks
basic.forever(function() {
    basic.showNumber(0)
})
```

### Step 2

Get a ``||input:temperature||`` block and place it in the value slot of ``||basic:show number||``.

```blocks
basic.forever(function() {
    basic.showNumber(input.temperature())
})
```

### Step 3
Add a pause of one second between displaying temperatures by dragging the ``||basic:pause||`` block below the ``||input:temperature||`` block. Choose '1 second' from the drop down menu.  


```blocks
basic.forever(function() {
    basic.showNumber(input.temperature())
    basic.pause(1000)
})
```

### Step 4 - Record the temperature
Now we need to set up your table to track the temperature. Drag ``||datalogger:set columns||`` into the ``||basic:on start||``
block.

```blocks
datalogger.setColumnTitles(" ")
```

### Step 5
Name your first column by typing "temperature" in the value box of ``||datalogger:set columns||``.
```blocks
datalogger.setColumnTitles("temperature")
```


### Step 6 - Create a time loop
Every minute, we want to track the temperature and record it to our log. Drag the ``||loops:every||`` block into the workspace. Choose '1 minute' from the drop down menu. 

```blocks
loops.everyInterval(60000, function () {
})
```

### Step 7
Now drag the ``||datalogger:log data||`` block into the ``||loops:time loop||``. Select column "temperature" from the drop down menu. 
Get a ``||input:temperature||`` block and place it in the value slot of ``||datalogger:log data||``.

```blocks
loops.everyInterval(60000, function () {
    datalogger.log(datalogger.createCV("temperature", input.temperature()))
})
```

### Step 8 - Create a sensor
First we need to name our sensor. Open the ``||variables:Variables||`` menu and select 'Make a Variable'. Type "Water Level" into the pop up box. Drag and drop the ``||variables:set Water Level||`` block into the ``||basic:on start||`` block.

```blocks
datalogger.setColumnTitles("Temperature")
let Water_Level = 0
```

### Step 9
We're creating a tool to measure water levels using conductive tape and electricity. If water touches the conductive tape, the electrical loop is closed and a signal is sent to the micro:bit saying the corresponding ``||input:pins||`` were pressed.

### Step 10




### Step 15 -  Recording water levels
First we need to create a column in our table to track our water level readings. Add "Water Level" to the ``||datalogger:set columns||`` block.

```blocks
datalogger.setColumnTitles("Temperature", "Water Level")
```

### Step 10000
Get a ``||input:temperature||`` block and place it in the value slot of ``||basic:show number||``.
![An animation that shows how to drag a block and paint a heart](/static/mb/projects/flashing-heart/showleds.gif)

``||data logger:||`` 

```blocks
basic.forever(function() {
    basic.showNumber(input.temperature())
    basic.pause(1000)
})
```


## Activity 2

### Step 1

### Step 2

### Step 3


Congratulations, you did it!
    

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>


```package
datalogger
neopixel=github:microsoft/pxt-neopixel
```