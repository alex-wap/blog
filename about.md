---
layout: page 
title: About Me
permalink: /about/
---

Below is a detailed account of the stuff I've worked on in the past.
This is going to be considerably more verbose than my resume. I plan to
eventually provide a way to group this list by work domain, programing language,
etc., but for now there's just this table of contents.

* TOC
{:toc}

### KAUST Course Projects

   1. *Computing Systems:* I've implemented the following in the
      [xv6](http://pdos.csail.mit.edu/6.828/2012/xv6.html) kernel:
      * A system call that counts the number of free pages at any time.
      * A bitmap memory allocator to replace the current linked list one.
      * A shared memory abstraction for user-mode programs.

      See the [code](https://github.com/emaadmanzoor/xv6/branches).
 
   2. *Algorithms:* For our group project, we did a comparative study
      of two cardinality estimation algorithms for big streaming data.
      * [Adaptive Sampling](http://hal.archives-ouvertes.fr/docs/00/07/55/33/PDF/RR-1025.pdf)
      * [HyperLogLog](http://algo.inria.fr/flajolet/Publications/FlFuGaMe07.pdf)

      Our [project report](https://www.dropbox.com/s/xa8hir3x2zlwv31/CS260_Final_Report.pdf)
      has the empirical results. [Code](https://github.com/emaadmanzoor/streaming-unique-counting)
      is available too.

### Yahoo!
{: style="float:left; margin-bottom:0;"}

*July 2012 -- August 2013*
{: style="float:right; margin-bottom:0;"}

<div style="clear:both;" markdown="0"></div>

As a software systems engineer at Yahoo! R&D in Bangalore, I was a primary
member of the small (4 engineers) Timesense team. Our goal was to build systems
to rapidly detect real-world events, like earthquakes and celebrity deaths,
from large, noisy streams of user-generated content.

Here are a few resources describing the original approach, using language
models to classify trending queries, published back in 2010:

   * [Towards recency ranking in web search](http://www.wsdm-conference.org/2010/proceedings/docs/p11.pdf).
     *WSDM*, 2010.
   * [Yahoo! Real Time Search](http://www.slideshare.net/davtchev/yahoo-real-time-search-smx-march-2010-3320691).
     *SMX*, 2010.

During my tenure with Timesense, we worked with
[Storm](http://storm-project.net), [Kafka](http://kafka.apache.org),
and [HBase](http://hbase.apache.org/) to build a system enabling streaming
language models for event detection. This new system reduced our earlier
trend detection latency by over 80%.

We also expose the (currently very limited) Timesense API via
[YQL](http://developer.yahoo.com/yql/console/#h=select+*+from+timesense.trending+where+locale%3D'en-US').

On a related note, [Pranay Agarwal](http://www.cse.iitd.ac.in/~cs5080220/index.html)
collaborated with us on some very interesting approaches to Twitter
trend prediction, for his
[masters thesis](http://www.cse.iitd.ac.in/~cs5080220/TwitterNews.html).

I also led the organization of a science and math talk series,
in a session of which I gave a [talk on random forests](https://speakerdeck.com/emaadmanzoor/reviving-failed-classifiers-with-random-forests).

*[Go back to the contents index](#markdown-toc)*

### Tachyon
{: style="float:left; margin-bottom:0;"}

*May 2012 -- July 2012*
{: style="float:right; margin-bottom:0;"}

<div style="clear:both;" markdown="0"></div>

I was a research intern at [Tachyon](http://tachyon.in) between graduating
and starting work full-time at Yahoo!. I worked on an applied computer vision
problem, to convert mobile camera images of comic books into individual panels
suitable for mobile viewing. My mentor (and the CEO) is an
[MIT TR35 awardee](http://www2.technologyreview.com/TR35/Profile.aspx?TRID=868).

I performed a bunch of experiments, understood and evaluated many ideas from
machine learning and image processing, and eventually settled on a research
prototype that worked well in most cases. I also built an Android application
wrapping this research up into a usable tool. We call it Comicreel.

This is better understood in pictures (taken off
the [Tachyon Demos site](http://tachyon.in/demos.html)).

![Comicreel Overview](/images/comicreel-1.png)
{: style="border: 1px solid #000;"}

**Figure 1:** Overview
{:.caption}

Solving the problem involved a series of steps:

   * Dewarping: Book pages in camera images usually appear warped and skewed,
     depending on the angle at which the photograph was taken. We need flat
     panels.

![Comicreel Dewarping](/images/comicreel-2.png)

**Figure 2:** Dewarping
{:.caption}

   * Splitting Panels: A comic book page consists of a series of panels. We
     needed to cut these out and rearrange them in reading order.

![Comicreel Splitting](/images/comicreel-3.png)

**Figure 3:** Splitting the comic into panels
{:.caption}

   * Restoring Colour: The colours in camera images are usually noisy, have gradients,
     and faded. But we know that in a print comic, the artist simply filled the
     outlines with solid colours. We need to restore these colours.

![Comicreel Example 1](/images/comicreel-4.png)

**Figure 4:** Restoring colour
{:.caption}

Here is another sample of the end result of this process.

![Comicreel Example 2](/images/comicreel-5.png)

**Figure 5:** Another sample
{:.caption}

*[Go back to the contents index](#markdown-toc)*

### Yahoo!
{: style="float:left; margin-bottom:0;"}

*July 2011 -- December 2011*
{: style="float:right; margin-bottom:0;"}

<div style="clear:both;" markdown="0"></div>

I was an intern at Yahoo! R&D in Bangalore for a semester, on the Timesense
team. My work during this period was primarily to refactor the code to be
multi-threaded and easily extendable to accommodate different languages and
countries. I also designed and implemented a configuration system that cut
down the launch time of new locales from impossible to a few minutes.

I also implemented a prototype to detect trending search queries that were
niche to a specific geographic area, by running a geolocation-entropy
based ranking algorithm on the detected trending queries.

I was one of the 3 interns (out of 14 in total) offered a full-time position
after the internship.

*[Go back to the contents index](#markdown-toc)*

### BITS - Pilani Goa Campus
{: style="float:left; margin-bottom:0;"}

*August 2008 -- May 2012*
{: style="float:right; margin-bottom:0;"}

<div style="clear:both;" markdown="0"></div>

I pursued my undergraduate degree in computer science at the [Birla Institute
of Technology and Science - Pilani, Goa Campus](http://www.bits-pilani.ac.in/goa/).

#### Course Projects

   * For our data storage technologies and networks course, we (team of four)
     built a Beanstalkd cluster for the distributed estimation of π and
     matrix multiplication. I've written a [detailed
     blog post](http://eyeshalfclosed.com/blog/2012/03/17/throwing-darts/)
     about it. We were also selected to present a 3 hour tutorial on this
     at [PyCon India 2012](http://in.pycon.org/2012/funnel/pyconindia2012/55-simple-linux-cluster-with-python-and-beanstalkd).

      * PyCon India 2012 tutorial slides on [Speakerdeck](https://speakerdeck.com/emaadmanzoor/building-a-cluster-with-python-and-beanstalkd).
      * [Code](https://github.com/emaadmanzoor/beanstalkd-pycon2012-tutorial/) from the tutorial.
      * [Distributed π estimation code](https://github.com/emaadmanzoor/distributed-pi-estimation) from the course project.
      * [Distributed matrix multiplication code](https://github.com/racheesingh/Beanstalkd-Cluster) from the course project.

   * For the data storage technologies and networks
     reading group, we (a team of two)
     [presented a paper](https://speakerdeck.com/emaadmanzoor/qufiles-the-right-file-at-the-right-time)
     on quFiles: an abstraction for context-aware data adaptation.

   * For the programming languages and compiler design course, I wrote a
     [BibTex Database Compiler](https://github.com/emaadmanzoor/bib2sqlite).
     We were required to write code using Lex and Yacc that would parse a BibTex
     file and compile it into a database that could answer arbitrary SQL queries.
     My submission was one of the few that were selected and made available to
     the rest of the class as model submissions.

#### Teaching

   * *Programming languages and compiler construction:* As a professional
     assistant, I graded and helped design and evaluate the course project.
     We (team of two) wrote an [ASCII regular
     polygon generator](https://github.com/racheesingh/Regular-Polygon-Generator)
     This was used to test the students' course projects, which were required to
     parse ASCII regular polygons and determine the number of sides they have.

   * *Software development for portable devices:* I was one of the four students
     funded by Google in 2011 to help teach the semester-long Android application
     development course. We conducted laboratory sessions for the course,
     and also organized a day-long tutorial at the nearby College of Engineering
     in Ponda, Goa. I've shared my [courseware](http://bit.ly/emaadcourseware).

   * *[MIT Indian Mobile Initiative](http://globalchallenge.mit.edu/teams/view/148):*
     I was a student mentor for the initiative held at the university from July - August, 2011.
     This brought together students from across India to learn
     Android application development and acquire entrepreneurship skills
     in a summer-long course. I organized a lab session on Android sensors,
     and provided round-the-clock programming assistance.

#### Other Projects

   * I built a [teaching and learning tool](http://emaadmanzoor.github.io/graphy/)
     for graph algorithms, that lets you visualize algorithms step-by-step on graphs you can
     construct on the software canvas yourself. This has seen a few hundred downloads, and
     I've mentored 3 students extending it with additional algorithms and features. The
     project is [open source](https://github.com/emaadmanzoor/graphy/).

   * For the Indian government's Sakshat initiative, we (team of two) built a 3-D
     simulation of Foucalt's pendulum using EJS. We've
     [released the code](https://github.com/racheesingh/Physics-Simulations)
     and the simulation is
     [hosted by IIT-K](http://ictwiki.iitk.ernet.in/wiki/index.php/Animations_in_Physics)

   * I designed and developed the client-side of the
     [Waves 2010 website](http://www.bits-waves.org/2010/). The site is
     built to look attractive and load quickly on university campus
     networks in India, which are usually slow and block Flash. The
     [site is open-source](https://github.com/emaadmanzoor/openwaves2010).

*[Go back to the contents index](#markdown-toc)*

### Open Source

   * I was funded by the University of Massachusetts and Google to spend
     the summer from July - September, 2011,
     building a
     [Debian package
      for MVHub](https://code.launchpad.net/~emaadmanzoor/+archive/mvhub-devpkg).

   * I [contributed the proximity sensor](http://code.google.com/p/openintents/source/detail?r=3280)
     to the OpenIntents Sensor Simulator.

   * I [contributed
     a documentation patch](https://github.com/nolta/Winston.jl/issues/38)
     to Winston.jl, a plotting library for the Julia language.

   * I'm [published by O'Reilly](https://www.androidcookbook.com/Recipe.seam?recipeId=1229)
     in the Android Cookbook. I contributed a recipe on mocking GPS coordinates.

*[Go back to the contents index](#markdown-toc)*

### Awards

   * In June 2013, I was offered the Erasmus Mundus Category A scholarship
     by the  Language and Communication Technologies (LCT) consortium to
     pursue the Erasmus Mundus LCT Masters. The scholarship is awarded to only 4
     non-EU applicants.

   * In May 2013, I was offered (and accepted) the KAUST Fellowship to pursue
     my masters in computer science at KAUST. This $70,000 fellowship covers
     housing, tuition and a stipend.

   * In December 2011, we won Random Hack of Kindness in Bangalore with
     Twackboard, an Arduino-powered portable tracking device to be placed
     on school buses. The device tweets out to parents when the bus has
     arrived at the bus stop.

   * In January 2009, I was awarded the CDC Fellowship by the Ministry of Science
     and Technology of India for a project on the implementation of transparent
     and automated laboratory examination evaluation processes.

*[Go back to the contents index](#markdown-toc)*

### Hacks

   * I [wrote some code](https://gist.github.com/emaadmanzoor/5019020) to
     download the Edinburgh first-story detection Twitter corpus.

   * We built [BMTCMiles](http://www.mybmtcmiles.com/) to encourage
     the use of buses in Bangalore. We extract the ticket cost from uploaded
     images of bus tickets using OCR (Tesseract) and assign reward points.

   * We built [Lyrebird](https://github.com/emaadmanzoor/lyrebird)
     so we could pretend we knew about everything anyone was talking about.
     It's hosted [here](http://lyrebird.herokuapp.com/).

   * I built [FindMeX](https://github.com/emaadmanzoor/findmex) as a local
     search engine for Android.

   * I wrote [pyFreeSMS](https://github.com/emaadmanzoor/pyFreeSMS) to send
     free text messages via 160by2. This is broken since 160by2 changed their
     website layout.

   * I wrote [xkcd.pl](https://github.com/emaadmanzoor/xkcd.pl) to sync
     xkcd comics to your local disk, with tooltips!

   * We plan to disrupt the restaurant ranking business with
     [Culinary Calipers](https://github.com/emaadmanzoor/culinarycalipers).

   * I wrote a [pure Python 2 implementation of linear and logistic
     regression](https://github.com/emaadmanzoor/python-ML-minimal).
     This is useful in programming competitions where external libraries
     are not allowed.

*[Go back to the contents index](#markdown-toc)*

### Online Courses

   * I took the first ever [ML-Class](http://bit.ly/mlclass-certificate) by
     Andrew Ng and scored 76.75/80 in the review exercises, and 800/800
     in the programming exercises. This course was the precursor to what is
     now Coursera.

   * I took the first ever [AI-Class](http://bit.ly/aiclass-certificate) by
     Sebastian Thrun and Peter Norvig and scored 89.9% in total. This course
     was the precursor to what is now Udacity.

*[Go back to the contents index](#markdown-toc)*

### Organizational Positions

These positions may not make sense to anyone outside of the BITS - Pilani University
system, but they involved a lot of blood, sweat and tears. I'll place them here
for anyone who appreciates that.

   * Coordinator, Waves 2010, Department of Publicity and Public Relations.
   * Chief Designer, 2009, Department of Publicity and Public Relations.
   * Core Member, Literary and Debating Club.
   * Core Member, Department of Journalism and Media Affairs.
   * Event Manager, Geek 'N Latin, Quark 2009.
   * Event Manager, Press Corps, Waves 2009.

*[Go back to the contents index](#markdown-toc)*

### Volunteer Work

   * I designed an [eye donation awareness video](http://www.youtube.com/watch?v=4GYvi0BYvks)
     for the Bangalore West Lions Superspecialty Eye Hospital.
   * I used to read to a blind scribe at the Abilities Home for the Blind,
     Bangalore.

*[Go back to the contents index](#markdown-toc)*
