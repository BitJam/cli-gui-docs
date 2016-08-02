# cli-gui-docs
Document the interface between our cli and gui programs

This will start out very rough.

## Menu Items

I need at least 3 break characters (if we include new-line) for
sending menu items.  This is because I need to use a break char
inside of the payload in order to have more than one field.

So the format for a menu item line is:

   item : $payload & $text

The text is the text to be displayed for this item and the
payload is what should be sent back to me if this item
in the menu is selected.  The spaces were added for clarity.

Actually we have four break characters here.  Perhaps that
is not ideal.  The first one is ":" after "item".  The
second one is "&" between the payload and the text.  The
third one is the new-line at the end of the line, which we
don't see here and the fourth one is the break character
inside of the playload that you don't need to know about.

It is easy for me to change the break characters.  Currently
I'm using:

    K_IFS="|"   # The break char used inside the payload
    P_IFS="&"   # The break char between payload and text
