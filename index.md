---
layout: lesson      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "Jazan University"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "DFL Training Hall, Faculty of Arts and Humanities, Jazan University, SA"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "sa"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "16.964200"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "42.547354"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Nov 06, 2024"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 12:00 pm UTC+3"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2024-11-05      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2024-11-05        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Dr. Abdulrahman Dallak"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
#helper: [""]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["adallak@jazanu.edu.sa"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: https://pad.carpentries.org/2024-11-05-06-dsju # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite: 1047463490497      # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
what3words:           # optional: what3words (https://what3words.com) address of the workshop venue, without leading slashes e.g. "globe.lessening.computers"
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}



{% comment %}
8< ============= For a workshop delete from here =============
For a workshop please delete the following block until the next dashed-line
{% endcomment %}




{% comment %}
8< ============================= until here ==================
{% endcomment %}

{% comment %}
Check DC curriculum
{% endcomment %}







<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}

<p>
<strong><a href="https://carpentries.org">The Carpentries</a></strong> project comprises the <a
href="{{site.swc_site}}">Software Carpentry</a>, <a href="{{site.dc_site}}">Data Carpentry</a>, and
<a href="{{site.lc_site}}">Library Carpentry</a> communities of Instructors, Trainers, Maintainers,
helpers, and supporters who share a mission to teach foundational computational and data science
skills to researchers.
<p align="center">
  <em>
  <strong>Want to learn more and stay engaged with The Carpentries?</strong> Carpentries Clippings is The Carpentries' biweekly newsletter, where we share community news, community job postings, and more.
Sign up to receive future editions and read our full archive: <a href="https://carpentries.org/newsletter/">https://carpentries.org/newsletter/</a>
  </em>
</p>
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% if site.pilot %}
This is a pilot workshop, testing out a lesson that is still under development. The lesson authors would appreciate any feedback you can give them about the lesson content and suggestions for how it could be further improved.
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://www.latlong.net/ to find the lat/long of an
address.
{% endcomment %}
{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
  {% if page.what3words %}
    What3Words location:
    <a href="https://what3words.com/{{page.what3words}}">///{{page.what3words}}</a>.
  {%endif %}
</p>
{% elsif online == "true_public" %}
<p id="where">
  <strong>Where:</strong>
  online at <a href="{{page.address}}">{{page.address}}</a>.
  If you need a password or other information to access the training,
  the instructor will pass it on to you before the workshop.
</p>
{% elsif online == "true_private" %}
<p id="where">
  <strong>Where:</strong> This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}; {{page.humantime}}
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong>
  {% if online == "false" %}
    Participants must bring a laptop with a
    Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  {% else %}
    Participants must have access to a computer with a
    Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  {% endif %}
  They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong>
  We are committed to making this workshop
  accessible to everybody. 
{% if online == "false" %}
  The workshop organizers have checked that:
<p>
  <ul>
    <li>The room is wheelchair / scooter accessible.</li>
    <li>Accessible restrooms are available.</li>
  </ul>
{% endif %}
</p>
<p>We are dedicated to providing a positive and accessible learning environment for all. 
  We do not require participants to provide documentation of disabilities or disclose any unnecessary personal information. 
  However, we do want to help create an inclusive, accessible experience for all participants. 
  We encourage you to share any information that would be helpful to make your Carpentries experience accessible.
  To request an accommodation for this workshop, please fill out the 
  <a href="https://carpentries.typeform.com/to/B2OSYaD0">accommodation request form</a>.
  If you have questions or need assistance with the accommodation form please <a href="mailto:team@carpentries.org">email us</a>.
</p>
<p>
  <a href="https://glosario.carpentries.org/">Glosario</a> is a multilingual glossary 
  for computing and data science terms. The glossary helps 
  learners attend workshops and use our lessons to make sense of computational and programming jargon written in English by offering it 
  in their native language. Translating data science terms also provides a teaching tool for Carpentries Instructors to reduce barriers 
  for their learners.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<p id="roles">
  <strong>Roles:</strong>
  To learn more about the roles at the workshop (who will be doing what),
  refer to <a href="https://carpentries.org/workshop_faq/#what-are-the-roles-of-everyone-participating-in-a-workshop">our Workshop FAQ</a>.
</p>

{% comment %}
WHO CAN ATTEND?

If you would like to specify who can attend the workshop,
you can use the section below.

Move the 'endcomment' tag above the beginning of the following
<p> tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:
- This workshop is open to affiliates to ABC university.
- This workshop is open to the public.
- If you are interested in attending this workshop, contact me@example.com
  for more information

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}



{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "incubator" %}
<p><a href="{{ site.incubator_pre_survey }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.incubator_post_survey }}">Post-workshop Survey</a></p>
{% elsif site.incubator_pre_survey or site.incubator_post_survey %}
<div class="alert alert-danger">
WARNING: you have defined custom pre- and/or post-survey links for
a workshop not configured for The Carpentries Incubator
(the value of `curriculum` is not set to `incubator` in `_config.yml`).
Please comment out the `incubator_pre_survey` and `incubator_post_survey` fields
in `_config.yml` or, if this workshop is teaching a lesson in the Incubator,
change the value of `carpentry` to `incubator`.
</div>
{% else %}
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}
<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to software as described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>
<hr/>
<div id="r">
  <h3>R</h3>

  <p>
    <a href="https://www.r-project.org">R</a> is a programming language
    that is especially powerful for data exploration, visualization, and
    statistical analysis. To interact with R, we use
    <a href="https://posit.co/products/open-source/rstudio/">RStudio</a>.
  </p>

  <div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#rstats-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#rstats-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#rstats-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

   <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="rstats-windows">
        <p>
          Install R by downloading and running
          <a href="https://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
          from <a href="https://cran.r-project.org/index.html">CRAN</a>.
          Also, please install the
          <a href="https://posit.co/download/rstudio-desktop/">RStudio IDE</a>.
          Note that if you have separate user and admin accounts, you should run the
          installers as administrator (right-click on .exe file and select "Run as
          administrator" instead of double-clicking). Otherwise problems may occur later,
          for example when installing R packages.
        </p>
        <h4>Video Tutorial</h4>
        <div class="yt-wrapper2">
        <div class="yt-wrapper">
        <iframe type="text/html" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" src="https://www.youtube-nocookie.com/embed/q0PjTAylwoU?modestbranding=1&playsinline=1&iv_load_policy=3&rel=0" class="yt-frame" allowfullscreen></iframe>
        </div>
        </div>
      </article>
      <article role="tabpanel" class="tab-pane" id="rstats-macos">
        <p>
          Install R by downloading and running
          <a href="https://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
          from <a href="https://cran.r-project.org/index.html">CRAN</a>.
          Also, please install the
          <a href="https://posit.co/download/rstudio-desktop/">RStudio IDE</a>.
        </p>
        <h4>Video Tutorial</h4>
        <div class="yt-wrapper2">
        <div class="yt-wrapper">
        <iframe type="text/html" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" src="https://www.youtube-nocookie.com/embed/5-ly3kyxwEg?modestbranding=1&playsinline=1&iv_load_policy=3&rel=0" class="yt-frame" allowfullscreen></iframe>
        </div>
        </div>
      </article>
      <article role="tabpanel" class="tab-pane" id="rstats-linux">
        <p>
          Instructions for R installation on various Linux platforms (debian,
          fedora, redhat, and ubuntu) can be found at
          <https://cran.r-project.org/bin/linux/>. These will instruct you to
          use your package manager (e.g. for Fedora run
          <code>sudo dnf install R</code> and for Debian/Ubuntu, add a ppa
          repository and then run <code>sudo apt-get install r-base</code>).
          Also, please install the
          <a href="https://posit.co/download/rstudio-desktop/">RStudio IDE</a>.
        </p>
      </article>
    </div>
  </div>
</div>
<hr/>
<h2 id="setup">Registration</h2>
{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<strong>Some adblockers block the registration window. If you do not see the
  registration box below, please check your adblocker settings.</strong>
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="500x"
  scrolling="auto">
</iframe>
{% endif %}
<hr/>
<!-- this is an html comment -->



