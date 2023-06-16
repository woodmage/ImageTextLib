# ImageTextLib
A library for writing text to an image.  Functions include:

ImageTextLib.ImageText it = new ImageTextLib.ImageText(Image image); //set image to initialize library
ImageTextLib.ImageText it = new ImageTextLib.ImageText(PictureBox picturebox); //use image from picturebox to initialize library

//get / set stuff:
it.SetPosition(PointF position); //set position to PointF position
it.SetPosition(float horizontal, float vertical); //set position to horizontal, vertical
it.SetPosition(); //set position to 0, 0
PointF pos = it.GetPosition(); //get position

it.SetMargins(RectangleF margins); //set margins to RectangleF margins
it.SetMargins(float left, float top, float right, float bottom); //set margins to left, top, right, bottom
it.SetMargins(); //set margins to 0, 0, 0, 0
RectangleF marg = it.GetMargins(); //get margins

it.SetFontName(string fontname); //set font name
string fname = it.GetFontName(); //get font name

it.SetFontFamily(FontFamily fontfamily); //set font family to fontfamily
it.SetFontFamily(string fontname); //set font family by fontname (equivalent to SetFontName(fontname))
FontFamily ffam = it.GetFontFamily(); //get font family

it.SetFontSize(float fontsize); //set font size
float fsize = it.GetFontSize(); //get font size

it.SetFontStyle(FontStyle fontstyle); //set fontstyle
FontStyle fstyle = it.GetFontStyle(); //get fontstyle

it.SetFont(Font font); //set font
it.SetFont(string fontname, [float fontsize = 16], [FontStyle fontstyle = FontStyle.Regular]); //set font using fontname and optionally fontsize and fontstyle
Font fnt = it.GetFont(); //get font

it.SetForeColor(Color forecolor); //set foreground color
it.SetForeColor(int red, int green, int blue, [int alpha = 255]); //set foreground color using red, green, blue, and optionally alpha
Color forec = it.GetForeColor(); //get foreground color

it.SetBackColor(Color backcolor); //set background color
it.SetBackColor(int red, int green, int blue, [int alpha = 255]); //set background color using red, green, blue, and optionally alpha
Color backc = it.GetBackColor(); //get background color

it.SetOutlineColor(Color outlinecolor); //set outline color
it.SetOutlineColor(int red, int green, int blue, [int alpha = 255]); //set outline color using red, green, blue, and optionally alpha
Color outlinec = it.GetOutlineColor(); //get outline color

it.SetOutlineSize(int outlinesize); //set outline size
int outlinesz = it.GetOutlineSize(); //get outline size

//Actual work functions:
it.Draw(string text, [bool clear = false], [bool breakonspace = true], [bool outline = false]); //draws text, optionally clearing the background, breaking on space, and outlining text
it.DrawIt(string text, [bool clear = false], [bool outline = false]); //draws text, optionally clearing the background and outlining the text
it.DrawText(string text, [bool clear = false]); //draws text, optionally clearing the background
it.DrawOutlineText(string text, [bool clear = false]); //draws text, optionally clearing the background
it.CarriageReturn(); //moves position to start of next line
it.DrawCenterText(string text, [bool horizontal = true], [bool vertical = false], [bool clear = false]); //draws text centered, optionally centering vertically and horizontally and clearing the background
it.DrawCenterOutlineText(string text, [bool horizontal = true], [bool vertical = false, [bool clear = false]); //like DrawCenterText but for outlined text
it.DrawRightText(string text, [bool clear = false]); //draw text flush with right border, optionally clearing the background
it.DrawRightOutlineText(string text, [bool clear = false]); //draw outlined text flush with right border, optionally clearing the background
SizeF sz = it.GetSize(string text, [bool outline = false]); //get size of text without drawing it, optionally size of outlined text

Note that the library defaults to using Courier New as the font name, 16 as the font size, and FontStyle.Regular as the font style.  Any
font parts set will cause all others to be generated.  The position defaults to 0, 0, and margins default to 0, 0, 0, 0.  These two can be
set back to defaults with a simple SetPosition() or SetMargins() command.  Foreground color defaults to black, background color defaults to
white, and outline color defaults to gray.  Outline size defaults to 1.
