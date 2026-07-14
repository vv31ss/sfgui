/*
    Library connection:
        enableHud(owner(), true)
        --@include sfgui/main.txt
        require("sfgui/main.txt")

    toggle GUI on/off with Alt

    Drawing:
        press E to draw
        press R to clear everything

    Creating an object:
        local object = GUI.Name(parent or nil)
        
    Change theme:
        GUI.setTheme(THEME.NAME)
    
    Miscellaneous:
        number = GUI.resX
        number = GUI.resY  // get screen resolution
        
        GUI.active  // guess what it does
    
    Functions for (almost) any object:
        :setPos(x, y)                    // set local position
        {x, y} = :getPos()               // get local position
        :setGlobalPos(x, y)              // set global position
        {x, y} = :getGlobalPos()         // get global position (position on screen)

        :setText(str)                    // set text (if applicable)

        :setSize(x, y)                   // set size
        {x, y} = :getSize()             // get size

        :setParent(object)               // parent to an object
        :unparent()                      // unparent

        :enableRendering(bool)           // enable/disable rendering
        :enableChildren(bool)            // enable/disable rendering of children

        :destroy()                       // destroy the object

        :topOrder()                      // make the object draw on top of others
        :downOrder()                     // make the object draw behind others
        bool = :onTop()                  // true if the object is last in the draw order

        :setScript(function(self), id or nil)   // function called every frame while the object is rendered
        :removeScript(id or nil)                // remove a script
        :enableScripts(bool)                    // enable/disable script execution

        bool = .destroyed               // true if :destroy() was called on the object

    Void:
        // empty object with no rendering

    Rect:
        // rectangle
        
    Text:
        // text

    Panel:
        // panel / window

        Button = .crossButton          // get the close button
        Button = .hideButton           // get the collapse button
        Context = .context             // get the context menu element (appears on right‑click of the header)
        Button = .context_closeButton  // close button inside the context menu
        Button = .context_hideButton   // hide/expand button inside the context menu

        :setClosedCallback()           // attach a function that fires when the window is closed

        bool = .hidden                 // check if the window is collapsed

    Button:
        // button

        :setPressedCallback(function)   // attach a function that fires once on left mouse press
        :setReleasedCallback(function)  // attach a function that fires once on left mouse release
        :setHoldingCallback(function)   // attach a function that fires every frame while left mouse is held

        Button:setDisabled(bool)        // if bool=true, the button cannot be pressed

        // can be parented to a Context

    Tab:
        // tab
        // child objects are only shown when the tab is active
        // best used together with TabHolder
    
    TabHolder:
        // tab holder
        // tabs parented to it will be displayed inside it
        // only one tab can be active at a time

        :setMaxTabSize(num)             // set the maximum length of a tab

    CheckBox:
        // checkbox

        :setCallback(function(bool))    // attach a function that fires on toggle; receives one argument (true=on false=off)

        bool = .active                  // true=on false=off; changing this triggers the callback
        
        :setSize(num) // change size
        
    List:
        // list

        :setArray(tbl)                  // set the array – must have indices 1,2,3… and contain strings

        :getSelected()                  // get the selected item
        :getSelectedIndex()            // get the index of the selected item

        :setSelectCallback(function(index, string))  // fires when the selected item changes; may also fire if the list changes and the selected item moves

        .buttonUp      // get the up button (cannot be destroyed)
        .buttonDown    // get the down button (cannot be destroyed)
        .slider        // get the slider (cannot be destroyed)

    TextEntry:
        // text input field

        :setSize(x)                     // set the width; height cannot be changed

        :setFinishInputCallback(function(text))    // attach a function that fires when input is finished; argument is the entered text
        :setInputChangedCallback(function(text))   // fires when the entered text changes; argument is the whole current text

        :enableCalculator(bool)         // enables automatic evaluation of expressions

    Context:
        // DO NOT USE!!!!!!!!!!!!!!!!!!!!!!!!!! NOT FINISHED
        // context menu
        // You MUST parent one or more buttons to it to use it
        // the context menu does not close automatically when a button is pressed; use :close()

        // cannot be parented to anything; must always be parented to root

        :open()     // open the context menu; always appears at the cursor position
        :close()    // close the context menu
        :setSize(x) // change width; height cannot be changed

    Slider:
        // slider
        // automatically decides whether to be vertical or horizontal based on its size

        :enableFill(bool)               // enable/disable background fill behind the handle (default true)

        :setValue(num)                  // set slider value (0–1)

        :setHandleSize(num)             // change handle size

        // num – a number from 0 to 1
        :setValueChangedOnceCallback(function(num))  // fires once when the slider is released; triggered by :setValue(num)
        :setValueChangedCallback(function(num))      // fires every time the value changes; triggered by :setValue(num)

        :setPressedCallback(function(num))   // fires once when the slider is grabbed
        :setHoldingCallback(function(num))   // fires continuously while the slider is being used
        :setReleasedCallback(function(num))  // fires once when the slider is released

    LineIndicator:
        // loading indicator???

        :setValue(num)                  // set progress (0 to 1)

    ToolTip:
        // text hint that appears when hovering over the object it is parented to

        :setText(string)                // change the text

        :show()     // force the tooltip to be always visible
        :hide()     // disable the forced show
    
    DropDownButton:
        // button with a dropdown selection list
        
        // right-click to cancel the selection
        
        // adding a selection:
            Button = :addSelection(string)
        // or
            // need to parent Buttons
            
        // by default nothing is selected (nil)
        
        :deselect() //select nil
        :select(string) //select the required element
        string = :getSelected() //get the selected element
        
        :setSelectionChangedCallback(function(string)) //triggers when the selection changes; if the selection is canceled, then string=nil
            
    AutoLayout:
        // a window inside which parented objects will be automatically arranged starting from the top left corner
        // to make AutoLayout arrange the objects, call :rearrange()
        // !not very smart!
        
        :show() // show outline
        :hide() // hide outline
*/






