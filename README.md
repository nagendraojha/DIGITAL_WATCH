# DIGITAL_WATCH
We created a circular clock GUI using tkinter with:

A canvas-based circular display

A real-time clock

Options to switch themes, colors, and font styles

A minimal, high-end UI/UX look, like a smartwatch or modern dashboard

🔍 Detailed Explanation
1. Class Structure
We used an object-oriented approach with a class:

python
Copy
Edit
class CircularLuxClock:
This encapsulates the entire clock logic for modularity and easier extension.

2. Window Setup
python
Copy
Edit
self.root.title("🕰️ Lux Circular Clock")
self.root.geometry("500x500")
This sets the title and fixed size of the window.

3. Canvas for Circular Shape
python
Copy
Edit
self.canvas = tk.Canvas(root, width=400, height=400, bg=self.bg_color, highlightthickness=0)
self.circle = self.canvas.create_oval(10, 10, 390, 390, ...)
We draw a perfect circle using create_oval, which gives it a luxurious, modern circular frame feel.

highlightthickness=0: Removes borders

outline=self.fg_color: Sets glowing border color

4. Live Clock Display
python
Copy
Edit
self.time_text = self.canvas.create_text(...)
self.update_time()
The create_text() function shows the current time in the center of the circle.

The update_time() method:

Calls strftime('%I:%M:%S %p') to get time like 04:15:36 PM

Updates every 1000 milliseconds (1 second) using after()

5. Themes
python
Copy
Edit
def light_theme() / def dark_theme()
These functions:

Change the background of both the root window and the canvas

Preserve the text and border color (glow)

🌓 You can toggle them from the "Theme" menu in the top menubar.

6. Color Toggle
python
Copy
Edit
def change_color()
Switches between teal (#00FFC6) and orange (#FF8C00) glow outlines + text.

It updates both:

Circle border color

Time text color

7. Font Toggle
python
Copy
Edit
def change_font()
This cycles through:

Georgia

Courier

Helvetica

Comic Sans MS

You can click “Customize → Change Font” to change the feel of the clock.

8. Menubar UI
python
Copy
Edit
menubar = tk.Menu(self.root)
We create a clean, Mac/Windows-style menubar with 2 dropdowns:

🎨 Theme: Light / Dark

⚙ Customize: Color / Font style

✅ Final Look and Feel
You end up with a classy circular clock, centered in the window, with:

Glowing border

Smooth animations

Interactive options for customization

Feels like it belongs in a luxury app or dashboard
