# uiz
# uiz

### A simple UI module built off PyQt5

uiz is a simple GUI/UI module built using PyQt5. uiz is designed to be simple, and opensource. You can check out the code on GitHub at zPointless/uiz. You may setup the module either way. uiz is still a work in progress - but it is compatible with PyQt5. To use PyQt5 widgets in uiz, you can open a App and then use app.new_window(). This will return a `Window()` object. The attribute `Window().window` is a PyQt5 QWidget, such you can add things to it. Using uiz Elements, they are accessible at `uiz.Elements.{element_name}.` Here's a quick guide on using uiz:

## Installation
uiz is avalible on pip. Simply run:
```
pip install uiz
```
DO NOT Download it from github unless you are a experienced dev - I didn't add the LICENSE, etc. to GitHub


## Initializing
uiz can be initialized easily. Start by importing uiz.
```python
import uiz
```
Next, setup an app, and a window.
```python
import uiz

app = uiz.App()
window = app.newWindow('Window Title',1000,1000)
```
In this case, we are creating a 1000x1000px window. You can now setup some elements.
```python
import uiz

app = uiz.App()
window = app.newWindow('Window Title',1000,1000)

text_element = uiz.Elements.Text('Hello World!', 'Courier New')
def on_press():
    print('button')
button_element = uiz.Elements.Button('Press me!',on_press, 'Courier New')
```
Lets display them on the window.
```python
import uiz

app = uiz.App()
window = app.newWindow('Window Title',1000,1000)

text_element = uiz.Elements.Text('Hello World!', 'Courier New')
def on_press():
    print('button')
button_element = uiz.Elements.Button('Press me!',on_press, 'Courier New')

text_element.show(window)
button_element.show(window)
# Or you can use window.show_element(button_element)
```
Finally, let's run the app.
```python
import uiz

app = uiz.App()
window = app.newWindow('Window Title',1000,1000)

text_element = uiz.Elements.Text('Hello World!', 'Courier New')
def on_press():
    print('button')
button_element = uiz.Elements.Button('Press me!',on_press, 'Courier New')

text_element.show(window)
button_element.show(window)
# Or you can use window.show_element(button_element)

app.run()
```
Of course, I have only demonstrated one of the many functions of the uiz module. This is a partial guide, and the uiz module isn't very well documented. Hopefully one day it could be better, but if you have anything for me to add or stuff like that, tweet out to @wx9cw, thanks for the support!


## Demo Program
```python
from uiz import App, Elements

# Instantiate the App
app = App()

# Create a window
window = app.newWindow("Demo Window", 800, 600)

# Button press function
def onPress():
    webv.setHTML(textarea.getText())

# Examples of each element

# Button
button = Elements.Button('Show HTML', onPress, font="Arial")
button.move(50, 50)
window.showElement(button)

# Text Area
textarea = Elements.TextArea('HTML from Text', font="Arial")
textarea.setGeometry(50, 100, 300, 200)
window.showElement(textarea)

# WebView
webv = Elements.WebView()
webv.setGeometry(400, 100, 300, 200)
webv.setHTML('<h1>Welcome to the WebView!</h1>')
window.showElement(webv)

# Image
img = Elements.Image('path/to/your/image.jpg')  # Adjust the path accordingly
img.setGeometry(50, 350, 300, 200)
window.showElement(img)

# Checkbox
checkbox = Elements.Checkbox('Check me')
checkbox.setGeometry(400, 350, 100, 30)
window.showElement(checkbox)

# RadioButton
radio_button = Elements.RadioButton('Radio Button')
radio_button.setGeometry(550, 350, 150, 30)
window.showElement(radio_button)

# ComboBox
combo_box = Elements.ComboBox(['Option 1', 'Option 2', 'Option 3'])
combo_box.setGeometry(50, 550, 150, 30)
window.showElement(combo_box)

# ProgressBar
progress_bar = Elements.Progressbar()
progress_bar.setGeometry(250, 550, 200, 30)
progress_bar.setValue(50)
window.showElement(progress_bar)

# Slider
slider = Elements.Slider()
slider.setGeometry(500, 550, 200, 30)
slider.setValue(75)
window.showElement(slider)

# Run the application
app.run()
```
