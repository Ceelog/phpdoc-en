General considerations
======================

A completely secure system is a virtual impossibility, so an approach
often used in the security profession is one of balancing risk and
usability. If every variable submitted by a user required two forms of
biometric validation (such as a retinal scan and a fingerprint), you
would have an extremely high level of accountability. It would also take
half an hour to fill out a fairly complex form, which would tend to
encourage users to find ways of bypassing the security.

The best security is often unobtrusive enough to suit the requirements
without the user being prevented from accomplishing their work, or
over-burdening the code author with excessive complexity. Indeed, some
security attacks are merely exploits of this kind of overly built
security, which tends to erode over time.

A phrase worth remembering: A system is only as good as the weakest link
in a chain. If all transactions are heavily logged based on time,
location, transaction type, etc. but the user is only verified based on
a single cookie, the validity of tying the users to the transaction log
is severely weakened.

When testing, keep in mind that you will not be able to test all
possibilities for even the simplest of pages. The input you may expect
will be completely unrelated to the input given by a disgruntled
employee, a cracker with months of time on their hands, or a housecat
walking across the keyboard. This is why it's best to look at the code
from a logical perspective, to discern where unexpected data can be
introduced, and then follow how it is modified, reduced, or amplified.

The Internet is filled with people trying to make a name for themselves
by breaking your code, crashing your site, posting inappropriate
content, and otherwise making your day interesting. It doesn't matter if
you have a small or large site, you are a target by simply being online,
by having a server that can be connected to. Many cracking programs do
not discern by size, they simply trawl massive IP blocks looking for
victims. Try not to become one.
