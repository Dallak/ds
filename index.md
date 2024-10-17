---
layout: lesson      # DON'T CHANGE THIS.
root: .
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "Jazan University"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "DFL Training Hall"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "sa"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "45"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Nov 05-06, 2024"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 12:00 pm UTC+3"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2024-11-05      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2024-11-06        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Dr. Abdulrahman Dallak"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
#helper: [""]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["adallak@jazanu.edu.sa"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: https://pad.carpentries.org/2024-11-05-06-dsju # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite: 1047463490497      # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
what3words:           # optional: what3words (https://what3words.com) address of the workshop venue, without leading slashes e.g. "globe.lessening.computers"
permalink: index.html 
---


This lesson is a general introduction to the statistical program R, which will give 
you foundational skills for doing exploratory data analysis. 
Our sessions will be very hands-on, with a strong emphasis on data visualisation and 
manipulation using a collection of packages known as the [`tidyverse`](https://www.tidyverse.org/). 

We will use a generic dataset from the [Gapminder Foundation](https://www.gapminder.org/), 
but the skills we learn here apply to a wide range of datasets. 

Along the way, we will not just learn _R_ itself, but also (and importantly) about 
fundamental principles of exploratory data analysis. 
In that sense, R will be taught as a tool that gives us the freedom to ask a range 
of questions from our data in a reproducible manner. 
We will discuss topics such as how to critically evaluate the quality of our data, 
how it can be used to answer specific questions, explore sources of variation, 
what makes a good visualisation, how to deal with missing data, and so on. 


<!-- this is an html comment -->

{% comment %} This is a comment in Liquid {% endcomment %}

> ## Prerequisites
>
> **These lessons assume no prior knowledge of the skills or tools covered.**
> 
> You will need a computer with a working copy of **R** and **RStudio**.
> Please make sure to install everything *before* working through this lesson.
> 
> Follow the instructions on the "[Setup](setup.html)" tab to install the software 
> and download the necessary data. 
{: .prereq}

{% include links.md %}
