# The promisingly- yet misleadingly-named Auto Layout

Wrangling views around on iOS and OS X

A view ~= a div, or any other visual element.

Springs and struts: a view and its superview. Nothing else.

![Springs and struts screenshot]()

Plus a whole bunch of supporting code.

Imagine:

A view contains some text with an image below it. The whole thing has a background colour. You have to size the image, size the label, size the outer view. The content might drive the size, the container might have to constrain the size. Yay for code!

![Picture of the hierarchy]()

Autolayout lets you use this instead:

a = mb + c;

* Location
* Size

Equalities and inequalities.

Kind of. It *is* a system of linear equations that the OS solves to make it all make sense. That's the fun maths bit. Actually, though, it's pretty magic.

Align the horizontal centres of the views.
Keep the label Y pt below the image.
Size the image (intrinsic sizes).
Size the label (intrinsic sizes).
Size the container.
Make sure there's a bit of padding around the whole thing.

Constraints are objects! You can add them, remove them, and modify them at runtime.

In fact, animation.

# Demo

Lay out the thing in IB? Wee OS X app.

# Working with constraints

* IB
* Visual language
* NSLayoutConstraint instances

# Things to remember

* The layout engine can't read your mind:
  * conflicts
  * ambiguity
* It can't evenly space multiple views. The system needs some help, so you need to calculate the contraints and apply them in code at runtime.
* Rewards a methodical approach. Add your constraints as you build up your view hierarchy. Inside out or outside on doesn't matter - but you need to be methodical rather than just throwing them at the views.
* It does actually make sense :)
* But there is a bit of a learning curve.
* Can be quite resource intensive. If you don't need the magic, or are slinging around 10000 rows in a table, you might be better off without.

# Resources

* WWDC videos
* [iOS Auto Layout Demystified](http://www.amazon.co.uk/Auto-Layout-Demystified-Mobile-Programming-ebook/dp/B00C68XS0S) by Erica Sadun
* [Using Auto Layout in UITableView for dynamic cell layouts & variable row heights](http://stackoverflow.com/questions/18746929/using-auto-layout-in-uitableview-for-dynamic-cell-layouts-variable-row-heights) on StackOverflow.
