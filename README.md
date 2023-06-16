# ImageTextLib
A library for writing text to an image.  Functions include:

`ImageTextLib.ImageText it = new ImageTextLib.ImageText(Image image);` sets image to initialize library

`ImageTextLib.ImageText it = new ImageTextLib.ImageText(PictureBox picturebox);` uses image from picturebox to initialize library

## get / set stuff:
`it.SetPosition(PointF position);` sets position to PointF position

`it.SetPosition(float horizontal, float vertical);` sets position to horizontal, vertical

`it.SetPosition();` sets position to 0, 0

`PointF pos = it.GetPosition();` gets position

`it.SetMargins(RectangleF margins);` sets margins to RectangleF margins

`it.SetMargins(float left, float top, float right, float bottom);` sets margins to left, top, right, bottom

`it.SetMargins();` sets margins to 0, 0, 0, 0

`RectangleF marg = it.GetMargins();` gets margins

`it.SetFontName(string fontname);` sets font name

`string fname = it.GetFontName();` gets font name

`it.SetFontFamily(FontFamily fontfamily);` sets font family to fontfamily

`it.SetFontFamily(string fontname);` sets font family by fontname (equivalent to SetFontName(fontname))

`FontFamily ffam = it.GetFontFamily();`  gets font family

`it.SetFontSize(float fontsize);` sets font size

`float fsize = it.GetFontSize();` gets font size

`it.SetFontStyle(FontStyle fontstyle);` sets fontstyle

`FontStyle fstyle = it.GetFontStyle();` gets fontstyle

`it.SetFont(Font font);` sets font

`it.SetFont(string fontname, [float fontsize = 16], [FontStyle fontstyle = FontStyle.Regular]);` sets font using fontname and optionally fontsize and fontstyle

`Font fnt = it.GetFont();` gets font

`it.SetForeColor(Color forecolor);` sets foreground color

`it.SetForeColor(int red, int green, int blue, [int alpha = 255]);` sets foreground color using red, green, blue, and optionally alpha

`Color forec = it.GetForeColor();` gets foreground color

`it.SetBackColor(Color backcolor);` sets background color

`it.SetBackColor(int red, int green, int blue, [int alpha = 255]);` sets background color using red, green, blue, and optionally alpha

`Color backc = it.GetBackColor();` gets background color

`it.SetOutlineColor(Color outlinecolor);` sets outline color

`it.SetOutlineColor(int red, int green, int blue, [int alpha = 255]);` sets outline color using red, green, blue, and optionally alpha

`Color outlinec = it.GetOutlineColor();` gets outline color

`it.SetOutlineSize(int outlinesize);` sets outline size

`int outlinesz = it.GetOutlineSize();` gets outline size


## Actual work functions:

`it.Draw(string text, [bool clear = false], [bool breakonspace = true], [bool outline = false]);` draws text, optionally clearing the background, breaking on space, and outlining text

`it.DrawIt(string text, [bool clear = false], [bool outline = false]);` draws text, optionally clearing the background and outlining the text

`it.DrawText(string text, [bool clear = false]);` draws text, optionally clearing the background

`it.DrawOutlineText(string text, [bool clear = false]);` draws text, optionally clearing the background

`it.CarriageReturn();` moves position to start of next line

`it.DrawCenterText(string text, [bool horizontal = true], [bool vertical = false], [bool clear = false]);` draws text centered, optionally centering vertically and horizontally and clearing the background

`it.DrawCenterOutlineText(string text, [bool horizontal = true], [bool vertical = false, [bool clear = false]);` like DrawCenterText but for outlined text

`it.DrawRightText(string text, [bool clear = false]);` draws text flush with right border, optionally clearing the background

`it.DrawRightOutlineText(string text, [bool clear = false]);` draws outlined text flush with right border, optionally clearing the background

`SizeF sz = it.GetSize(string text, [bool outline = false]);` gets size of text without drawing it, optionally size of outlined text

### Notes
The library defaults to using Courier New as the font name, 16 as the font size, and FontStyle.Regular as the font style.  Any font parts set will cause all others to be generated.  The position defaults to 0, 0, and margins default to 0, 0, 0, 0.  These two can be set back to defaults with a simple SetPosition() or SetMargins() command.  Foreground color defaults to black, background color defaults to white, and outline color defaults to gray.  Outline size defaults to 1.

The shortest and simplest code to use this library is:

```
Bitmap bitmap = new Bitmap(100,100); //make a new bitmap
ImageTextLib.ImageText it = new ImageTextLib.ImageText(bitmap); //set up imagetext object using bitmap
it.draw("This is to test the ImageTextLib library."); //draw some text to the imagetext object
pictureBox1.Image = bitmap; //set picturebox to use bitmap
pictureBox1.Invalidate(); //tell windows to repaint the picturebox
```

I hope you find this library useful!