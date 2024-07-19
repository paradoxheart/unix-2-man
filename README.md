# unix-2-man
Project to reverse engineer the Unix 2nd Edition Manual from the scanned version of Joe Ossanna's copy

So far, the title and intro pages are mostly completed, with a few issues:

- This is not strictly an acurate representation of the copyright symbol, which appeared to use a plain letter `c`, shifted vertically half a line by the printer, and someone manually ringed the `c` after printing to form the symbol. I have inserted the control codes to do the vertical shift.
- Modern nroff expects you to use macros to lay out the vertical margins on pages. Macros did not exist prior Joe Ossanna's nroff, which is normally credited as being release in Unix 3, in February 1973. This is about six months after the release of Unix 2 in June 1972. The Unix 2 manual's table of contents has an entry for nroff, but the page is missing. As such it is ambigious whether or not the Unix 2 manual could have been produced with macros, or if they came later. nroff was most likely already in development when the Unix 2 manual was produced, but there is no way to know how far along it would have been at the time.
- For similar reasons, I am unsure if three part titles should be used to compose the page numbers in this document.
- I am currently wrapping long lines of text at the place they wrap in the scanned document. I should check if teletypes match up with this column width, or if they are typically 80 columns like glass terminals. If the latter, perhaps it is better to wrap at around 80 columns, and let roff's layout routines work their magic.
- It seems like control codes are normally lower case in modern roff, but I should check period documents to see if uppercase was more common.
- Apparently classical nroff magically output two spaces instead of one after the end of a sentence. Current groff doesn't seem to do this, and I haven't discovered a way to turn it on it yet. Spaces are manually added for the moment.
