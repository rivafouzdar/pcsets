## Updates ##

**2-May-2009** _News about a related project, and about version 3 of pcsets [on my Wordpress blog](http://bmccosar.wordpress.com/2009/05/02/in-progress-gpcsets-pitch-class-sets-for-haskell/)._

**26-Apr-2008** _The main pcsets module has been remarkably stable.  I have tried to rewrite
sections of it from time to time, but have found it hard to improve._

_However, it now has a derivative.  I've begun experimenting with
microtonal music.  One of my finds was an unusual system called the
[Bohlen-Pierce](http://pcsets.googlecode.com/files/bpsets-experimental-0.1.zip) scale -- 13 tones that span a 'tritave' (two notes with
a frequency ratio of 3:1, as opposed to the 2:1 octave)._

_If you're interested, you can download
[the experimental bpsets module](http://pcsets.googlecode.com/files/bpsets-experimental-0.1.zip) (zip archive, 22K).  For everyone
else that's found this page, you're probably safe in moving on to
more familiar territory, below..._ ;-)

# pcsets: Pitch Class Sets for Python #

_version 2.0.2_

Bruce H. McCosar


Welcome! This is the third
official release of pcsets.
This package features the first two chapters of a tutorial
and a few new abilities for pcsets.tonerow.

Learning about Pitch Class Sets is easy -- the four modules presented
here are, like many Python programs, self documenting. They work well
with pydoc <http://docs.python.org/lib/module-pydoc.html>.

Learning how to use these for practical compositional purposes, on the
other hand ... well, that takes a lot of individual experimentation. In
future releases of this module, I will include a short tutorial, and
demonstrate some of the techniques I've learned. However, you are a much
better judge of what you want to know than I -- please, try the module
out, and most of all, have fun learning something new.

## About Pitch Class Sets ##

Pitch Class Sets are a mathematical model for analyzing and composing music. Each note 'C' through 'B' has an equivalent pitch class number 0 through 11. Sets of these numbers may be operated on by mathematical functions such as transpose and invert.

The goal of this project is to, eventually, have:

  * A Python library capable of fully implementing Pitch Class Sets and their common operations, as well as several convenience functions to bring these abstract concepts to the real world.  (Mapping pitch classes to note names, for instance).
  * A tool for composition.  Some applications are harmonization, chord voicing generation, and melodic motif creation.
  * More exotic goals -- creation of new chordal elements, musical progressions, and harmonic relationships.

As you can see, these goals range from easy (already implemented) to
insanely difficult!

## Why ##

I became interested in pitch class sets as an offshoot of my earlier
work in jazz (see 'About the Author', below). At the end of this
file is a list of text and Web references that might provide an
introduction to the theory.

I decided to write a Python module after finding most of the programs
available online were GUI-only / interactive only (or worse . . .
applets). For various reasons, I needed to be able to set up long
computational chains on a group of pitch class sets. Typing them into
a web browser one at a time and poking buttons was **not** an option!

I released the module to the public under the GPL for three reasons:

  1. It might serve as an educational tool for music theory and Pitch Class sets.
  1. The addition of functions to connect set theory to the more traditional chord/scale theory might lead to innovative, new types of music software.
  1. There wasn't a module available that provided the same functionality.

On the other hand, here I am, publishing a module that requires the
end user to be knowledgeable about 1.) Python and 2.) Musical Set
Theory (obscure).  So I don't expect to be the next GNU grep.

## About this Package ##

The API will not change for any of the modules referred to as 'core'.
Bugs will be fixed and new modules will be added, but you won't wake
up one day and find that PcSets wants input in statcoulombs or Dutch
Guldens. In the version 2 series, the core will always behave like
the core. Occasionally new functionality will be introduced, but the
original functionality will never be 'broken' -- that's why I spent all
that time writing unit tests.

This is the core as of 2.0.0:

  * **pcsets.pcset** -- The base class. Includes methods that operate on single sets, such as inversion and transposition.
  * **pcsets.pcops** -- Operations on two or more sets, such as subset\_of(a,b).
  * **pcsets.catalog** --Generates the entire catalog of 224 prime sets as a Python object. Since this takes a while to generate, it saves the catalog in a pickle file (catalog.pkl) for future use.
  * **pcsets.noteops** -- The 'universal translator' from PcSets to named notes and vice versa.

Any **new** modules will enter as 'experimental', however, not core.
Experimental modules can change at any time.

With version 2.0.1, I introduce the first experimental module:

  * **pcsets.tonerow** -- Implements the ToneRow class.  Unlike PcSets, which are unordered, a ToneRow consists of all 12 pitches in an **ordered** arrangement.

There is a lot of good information on this subject in the Straus book
referenced below. I've also put a lot of time into writing documentation
strings for the module; a run through it with pydoc will probably tell
you somewhere between too much and _far_ too much ;-)

Another experimental module in development (and still in hiding,
until I settle on a usable, workable interface):

  * Operations on the familiar chords and scales -- sort of a noteops for the common language of chord-scale theory.

These modules won't make it to the core until at least version 2.1.


--BMC


## About the Author ##

Bruce H. McCosar is a middle and high school science teacher residing
in Gainesville, Florida; he switched to teaching after a career in
medicinal chemistry. He is a member of the Mvskoke (Creek) Nation.

Besides a lifelong interest in science, Bruce is a musician. He plays
bass guitar, electric guitar, Hammond organ, and conga drums.

In 2006, he began releasing his music online under a Creative Commons
license for free download at Jamendo. So far he has four albums,
available from his artist page at:

> http://www.jamendo.com/us/artist/bruce.h.mccosar/

And if all that wasn't enough, he then got into Python programming!


## References ##

I'm not one of those that's going to post a zillion references just to prove I can read. These are the best, the most helpful, the ones I look at all the time. That's right, I read wholesale and passed the savings on to you!

### Web ###

  * I posted a lot of the earlier Pitch Class Set code to my blog (bad idea ... it mangled the \n type characters). Nevertheless, there's some good discussion and examples.  Check under the tags 'music theory' or 'python'.

> http://bmccosar.wordpress.com/


  * If you want a short introduction or tutorial, Jay Tomlin's site is the best. Sort of the 'Classics Illustrated' of Pc theory.

> http://www.jaytomlin.com/music/settheory/help.html


  * If you want a LOT of information without chasing down a book, well... here's the next best thing. The author does get upset about the old '037' vs '047' issue. You'll see.

> http://solomonsmusic.net/setheory.htm


### Text ###

  * The classic of the field, "The Structure of Atonal Music", by Allen Forte (1973).

  * A relatively new (but extremely thourough and readable) work, "Introduction to Post-Tonal Theory", by Joseph Straus (3rd ed., 2005).