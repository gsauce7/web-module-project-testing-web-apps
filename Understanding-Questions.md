# Understanding Questions:
1. What are some possible tests for this application?
* The component correctly renders.
* ...

In addition to the ones already specified in the readme:

-> Test that a user can't enter a number into First Name or Last Name field and a warning is displayed if so

-> Test that Message will allow unlimited size, so the end user's right to free speech will not be infringed!

-> A realistic name can be any length, so long as it's 1 character or more but... I'd make it 50 characters maximum and test for such

https://ux.stackexchange.com/questions/55529/what-should-the-character-limits-for-first-last-name-inputs-be

QUOTE:

"In practice that is not possible to implement.

There have to be limitations.

These limitations can be subjective, such as what constitutes a "real" name so that you don't end up with names like :

aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

To this end Facebook, for example, has a fairly straight forward set of constraints they enforce:

Names can't include:

Symbols, numbers, unusual capitalization, repeating characters or punctuation
Characters from multiple languages
Titles of any kind (ex: professional, religious, etc)
Words, phrases, or nicknames in place of a middle name
Offensive or suggestive content of any kind
Length is not explicitly mentioned, however according to this SO post the limit is currently 50 chars.

In Active Directory the Display-Name attribute is limited to 256 characters.

These are just two examples that vary. You could research multiple services to see what their length limits are, but the truth is you need to decide for yourself what is acceptable.

But why have a limit at all?!?
There is one limitation that is not subjective: security.

Any interface that accepts and internalizes user input absolutely must without question treat input as a threat that must be validated and sanitized. Input should be validated to ensure it is of the correct type, length, format, and range.

Input should be sanitized to prevent little bobby tables from ruining your day. But in the case where a weakness in your sanitation is discovered, the validation step (including checking for length) offers protection by limiting how the attacker can exploit a vulnerability.

There is another objective limitation: storage capacity.

There is nobody in any culture in the entire world that has a name that is legitimately 1,073,741,823 bytes long (the upper bound of a ntext data type in SQL Server). But even that is a limit which is a technical limitation of the data store.

So what should the limit be?
The problem is that no limit is not an option for several reasons; some arguably subjective while others objective, real, and unavoidable.

But we also don't want to have users be unduly constrained.

A well designed system will ensure that both needs are met without the user ever knowing that there is a limitation in place to begin with. It should be transparently secure and usable.

To that end, I think a reasonable limit should be (arbitrarily) 25% longer than the longest name in your current data set. Given a large enough sample, that should ensure you will be giving your users enough "breathing room but not allowing a malicious user to try to exploit your system.
