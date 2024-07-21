# unix-2-man
Project to reverse engineer the Unix 2nd Edition Manual from the scanned version of Joe Ossanna's copy

So far, the title and intro pages, table of contents, and index are completed, with a few issues:

- I am currently wrapping long lines of text at the place they wrap in the scanned document. Given that I don't know the exact model of teletype that was used to write the manual, I think it best to wrap at the same point in the source file unless otherwise required due to control codes. The Teletype Model 33 was commonly paired with the PDP-7 that Unix 2 was written for, however that teletype appears to support only upper case text, and the manual is mixed case. It is therefore possible that they were using a later Teletype model, or perhaps an IBM teleprinter that supported mixed case instead. The Model 33 supported either 72 or 74 characters (depending on source), but other contemporary models supported 80 or even 132 characters. I don't currently have anything to suggest that a particular wrapping point for the source file is more accurate than any other.
- This is not strictly an acurate representation of the copyright symbol, which appeared to use a plain letter `c`, shifted vertically half a line by the printer, and someone manually ringed the `c` after printing to form the symbol. I have inserted the control codes to do the vertical shift. This may give some clues about the type of teletype in use. Models which do not support this feature should be discarded as candidates.
- The description of kbd, login, and tabs in the miscelaneous section of the manual implies that the Teletype Model 37 was in the most common use. It's likely that they coded Unix 2 primarily for that teletype, while supporting others. Perhaps this indicates that the manual would have been written on a model 37.
- Modern nroff expects you to use macros to lay out the vertical margins on pages. Macros did not exist prior Joe Ossanna's nroff, which is normally credited as being release in Unix 3, in February 1973. This is about six months after the release of Unix 2 in June 1972. The Unix 2 manual's table of contents has an entry for nroff, but the page is missing. As such it is ambigious whether or not the Unix 2 manual could have been produced with macros, or if they came later. nroff was most likely already in development when the Unix 2 manual was produced, but there is no way to know how far along it would have been at the time. I have settled on using macros following the examples in the Troff User's Manual, as it is likely that the same authors would adopt the same patterns if macros were available.
- It seems like control codes are normally lower case in modern roff, but I should check period documents to see if uppercase was more common.
- Classical nroff output two spaces instead of one after the end of a sentence. Current groff leaves this up to the document author, unless the sentences are separated by a new line, in which case it follows the behaviour of old nroff and adds two spaces. I will add the two spaces manually.

The following commands are available:
- :
- acct
- ar
- as (WIP)
