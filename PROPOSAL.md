**Name:** Jitesh Kumar Jha

**Affiliation (school/degree)** Manipal Institute of Technology, Manipal - 4th semester, Computer Science & Engineering

**Location (where you are):** Manipal, India

**Email:** jiteshjha96@gmail.com

**Phone:** +91-9591361570

**Github:** [jiteshjha](https://github.com/jiteshjha)

**Project(s) you're working on or want to**: Publiclab.org

**Project title**: Internationalization of Publiclab.org

## Project description

### Abstract/summary: 

Internationalization is the process of planning and implementing products and services so that they can easily be adapted to specific local languages and cultures, a process called localization. Internationalization of Publiclab.org will help different communities around the world facing environmental justice issues to easily work and contribute in the supported language of their choice and make the website universally accessible and useful.
### Describe the need your project fulfills: 

Currently,  languages are supported with tags. In case of Spanish, reasearch notes/wikis by 'lang:es' tag, with all the content posted in Spanish [here](https://publiclab.org/tag/lang:es). All the character sets are supported on the website, but elements like footer, header, sidebars, menus, posting forms, user profile, etc are still in default locale - English. Different language support while posting research notes/wiki and localization of website elements are crucial for true internationalization of Publiclab.org.
### How will your project meet this need: 

Internationalization of Publiclab.org will be achieved with  [rails-i18n](https://github.com/svenfuchs/rails-i18n). Primitively, the process will start with header and footer of Publiclab.org. The following step will be addition of locale yaml files for different languages with support from translation community for the layout of Publiclab.org. Rails supports "Lazy" lookup, hence different elements of the .erb views can be altered by simply issuing `t('.element')` instead of `.element`. This change will affect almost every line of the template. Separate preference field for the language in the User model and visual language switching controls in the header of the website will be implemented to enable the user to manually set the preferred language, and additionally HTTP header of the user will be analyzed to set the local language automatically. Existing Javascript libraries will also be internationalized similar to rails-i18n. After header and footer is internationalized, other parts of website like index, donate, user profile, posting forms will be internationalized in similar manner. New tests will be written so that the changes do not break any functionality of the existing codebase. Finally migration to sub-domains like 'fr.publiclab.org'( for French-speaking regions), etc. will be achieved. The overall process can be summarized into three points:


* Adaptation to locale.


* Translation of User interface.


* Translation of helps and getting-started docs.


* Migration to locale specific sub-domains.

### Timeline/milestones:

**Note: The whole process will be accomplished in stages, so that rebasing and merging doesn't pose any difficulties.**

##### **April 22, 2016 - May 22, 2016** [Community Bonding]


* Gain greater insight into [plots2](https://github.com/publiclab/plots2.git) codebase.


* Bond with the community members and become accustomed with the Publiclab.org's culture.


* Learn the tools and technologies necessary for the project.


* Start a blog on Publiclab.org about the project to help my mentor track my progress.


* Choose a platform for organizing translations efforts. [Since the development process for Publiclab.org is currently on Github, Github will a great place to start with].

##### **May 23, 2016 - June 06, 2016**


* Start with [header and footer](https://github.com/publiclab/plots2/issues/393).


* Use [rails-i18n](https://github.com/svenfuchs/rails-i18n) gem, add initial language support to [config/application.rb](https://github.com/publiclab/plots2/blob/master/config/application.rb).


* Create translations yaml files in [config/locales/*](https://github.com/publiclab/plots2/tree/master/config/locales).


* Insert [lazy-lookups](http://guides.rubyonrails.org/i18n.html#looking-up-translations) to [header](https://github.com/publiclab/plots2/blob/master/app/views/layouts/_header.html.erb) and [footer](https://github.com/publiclab/plots2/blob/master/app/views/layouts/_footer.html.erb).


* Gather translations work from the community and start preparing the yaml locale files.

##### **June 07, 2016 - June 20, 2016**


* Add language switching controls to the top-right of navigation bar.


* Create a controller for a new route to change locale. Update [config/routes.rb](https://github.com/publiclab/plots2/blob/master/config/routes.rb).

* Add a new column language_preferred to [user model](https://github.com/publiclab/plots2/blob/master/app/models/user.rb) and introduce new form field in Profile settings to accept the new attribute.

* In the controller created, use either cookies or language_preferred value of the user to store the language preferred in the controller.


* In [controllers/application_controller.rb](https://github.com/publiclab/plots2/blob/master/app/controllers/application_controller.rb), add the functionality to check cookie/language_preferred value of the user and adjust the locale for every page.


* Write integration tests for new/altered controllers.


* Write documentation of code so far, tidy up the site's codebase, clean up JS and CSS files.


* Any bugs encountered to this point or project goals not implemented yet to be tackled by this time.

##### **June 21, 2016 - June 28, 2016** [Midterm Evaluations]


* Mentors and students submit their evaluations of one another. These evaluations are a required step of the program.

##### **June 29, 2016 - July 27, 2016** [Most challenging weeks]


* For setting locale according to user's region, use Accept-Language: HTTP header with [http_accept_language](https://github.com/iain/http_accept_language).


* In [controllers/application_controller.rb](https://github.com/publiclab/plots2/blob/master/app/controllers/application_controller.rb), add the functionality to fetch user's location if preferred locale is not set. 


* Explore more ways to identify user's location from the [i18n-guide](http://guides.rubyonrails.org/i18n.html#setting-and-passing-the-locale).


* Write integration tests for the application controller.


* At this point, basic functionality of internationalization will be finished.


* Add support for more languages, and with translated yaml files with the help of community translations efforts in [config/locales/*](https://github.com/publiclab/plots2/tree/master/config/locales), move on to [home views](https://github.com/publiclab/plots2/tree/master/app/views/home), [user views](https://github.com/publiclab/plots2/tree/master/app/views/users), [dashboard views](https://github.com/publiclab/plots2/tree/master/app/views/dashboard).

* Handle internationalization of [javascript files](https://github.com/publiclab/plots2/tree/master/app/assets/javascripts) with [i18n-js](https://github.com/fnando/i18n-js).

##### **July 28, 2016 - August 15, 2016**


* Complete any remaining tasks/fix unresolved bugs.


* With sub-domains of Publiclab.org, [set up sub-domain locale](http://guides.rubyonrails.org/i18n.html#setting-the-locale-from-the-domain-name).


* These weeks will ideally be devoted to improving the site's UI.


* Deploy the site for community members for review and fix the bug(s) reported.


* Publicize the internationalization of Publiclab.org on [reddit](https://www.reddit.com/domain/publiclab.org).

##### **August 16, 2016 - August 24, 2016**


* Add documentation for all the new stuff written since Midterm evaluations. Tidy up the ugly parts.


* Language-addition tutorial for future developers to add new or enhance language support.


* Clean up the CSS and JS files, remove useless code from controllers.


* Add relevant comments to the ruby code.


* Submit sample code to the mentors.

##### **August 24, 2016 - August 30, 2016**


* Mentors review student code samples and determine if the students have successfully completed their Google Summer of Code 2016 project.

**************************

### What broader goal is your project working towards? 

Making Publiclab.org more genial and accessible to new and existing users and foster diversity.

### What resources will you need: people, documentation, literature, sample data, hardware if applicable: 


* Community Development team's help to choose a platform to collect translations from the community.


* Basic template translation of Publiclab.org in languages to be supported.


* Rails Internationalization (I18n) API [guide](http://guides.rubyonrails.org/i18n.html).


* Documentation for [i18n-js](http://www.rubydoc.info/gems/i18n-js/2.1.2) gem and [http_accept_language](http://www.rubydoc.info/gems/http_accept_language/2.0.5) gem.

### Setup


* [Forked repository](https://github.com/jiteshjha/plots2.git)
* [Development environment](https://c9.io/jiteshjha/plots2)


All the tests are passing on [c9.io](https://c9.io/jiteshjha/plots2).

### Experience


I have a decent amount of experience with Ruby, Javascript and Python. Also, I'm well versed with C/Java as they are in my college curriculum (Mostly worked on data structure and algorthims, as evident [here](https://github.com/jiteshjha/geeksforgeeks/tree/master/DataStructures), [here](https://github.com/jiteshjha/geeksforgeeks/tree/master/Algorithms) and [here](https://github.com/jiteshjha/LeetCode.git)). I started contributing to the university Computer Science club [website](https://iecse.xyz/) in Winter 2014, which sparked my interest in web development. Consequently, I have developed many projects mainly on Javascript(AngularJS) like [Realtime Markdown Editor](https://github.com/jiteshjha/Markdown-Editor), [Tabbed Browser](https://github.com/jiteshjha/nodewebkit-browser) and [StatusApp](https://github.com/jiteshjha/StatusApp). I have worked with databases like MySQL, Oracle SQL and MongoDB. I have been using Ubuntu/Opensuse Distro since 2011 and use Atom text editor with minimap and atom-linter packages.

I started learning development with Ruby on Rails a year ago with Michael Hartl's amazing [book](https://www.railstutorial.org/book). I interned at Firexit Software in Winter 2015, where I worked with the web-dev team to create a dashboard webapp with Ruby on Rails + [Highcharts](https://github.com/PerfectlyNormal/highcharts-rails) and the learning process was startling here. Again, to refresh my Ruby on Rails concepts, I have created a [RSS Reader](https://github.com/jiteshjha/RSS-Reader). I have also [contributed](https://github.com/publiclab/plots2/commits?author=jiteshjha) to [Publiclab.org](https://github.com/publiclab/plots2.git) repository. I am active in the Ruby On Rails Mumbai, India dev group where I have volunteered at many talks and events. I am also currently developing a [recommendation system](https://github.com/jiteshjha/Recommendation-System) in Python and plan to extend it to recommend user-based music recommendation.
In Microsoft Code.Fun.Do hackathon 2016, my app [Who's up - A networking app for Windows Platform](https://github.com/jiteshjha/who-s-up) - was voted 'One of the top 5' ideas from my university and is currently on the stage of getting published on the Windows App Store.

I have read the [Contributor Guidelines](https://publiclab.org/wiki/contributing-to-public-lab-software) and I am comfortable with git and submitting pull requests.

### Teamwork


During my internship at Firexit Software, I followed the coding style guide of the organization and coordinated with the team I was working with, to make different visual modules for the dashboard web app. During the process, I encountered many bugs which I fixed independently for my components. I'm well versed with the git pull request, compare and merge flow. Additionally, I am working with a teammate on a IMDB-like movie database webapp on Flask/Python for my Database Systems Lab, where we divide our work goals and merge our progress every week. I believe working in a team benefits the quality of code in general, speeds up the development and having a mentor is a great plus.

### Expertise


I reckon that I am good at problem - solving and web development and well suited for this proposed project. I am well versed with [plots2](https://github.com/publiclab/plots2.git) codebase and have strong experience with Rails and Javascript. Along with that, I have setup the development environment [here](https://c9.io/jiteshjha/plots2). I'm also acquainted with C/Java/Python and have extensive web application development experience through projects and past internships.  As a newcomer, I would like to utilize GSoC 2016 to get introduced to open source development. I'm impressed by the benefits of contributing to the open source, for both community and oneself. For instance, I tracked a bug which went unnoticed by new developers installing plots2 on cloud9, and created a [pull request ](https://github.com/publiclab/plots2/commit/cda77f7b8e2b3272a1199c7e535f46b50aff5188) which fixed the bug, ensuring smooth installation. Within a span of less than a month, I have fixed many small [issues](https://github.com/publiclab/plots2/commits?author=jiteshjha) and reported [issues](https://github.com/publiclab/plots2/issues?q=is%3Aissue+is%3Aclosed+author%jiteshjha) for Publiclab.org, while getting comfortable with [plots2 codebase](https://github.com/publiclab/plots2.git). I believe in creating pretty and responsive UI and UX , which is important for a pleasant and comfortable user experience. Hence, I consider myself to be particularly suited to the proposed project.

### Interest


I have prior interest in environmental justice and nature conservation goals. I took 'Environmental Education' as a subject in my first semester in university, and delivered a presentation on the composition of air pollutants from industries around our university town. I have previously volunteered in a mass plantation drive in my high school, where the school team covered small tracts of barren land with saplings. I have also worked on a tracking programme in summer 2014 for a local NGO in Navi Mumbai, India to track the disappearance of roadside Royal Poinciana trees. 

### Audience


The internationalization of Publiclab.org would serve the lay users from different regions around the world, primarily those who are willing to get started with Publiclab.org, but are unable to do so due to language barrier. The proposed project will lower the barrier for people whose native language is not English and will increase diversity.

### Context


I'd be elated if the proposal could be accepted, as it could allow me to make more advanced contributions to the open source. The idea of contributing to the open source and helping the non - technical people through coding and problem - solving skills is exciting; Development on Rails is easier and fun, and I would love to share my resources with those in need.

### Ongoing involvement


I intend to regularly contribute to the [plots2](https://github.com/publiclab/plots2.git) codebase and be involved in the mailing lists and developer IRC. I will continue contributing to [plots2](https://github.com/publiclab/plots2.git) codebase even after the GSOC 2016 programme. I'd like to volunteer later continuing this translation effort, helping with other languages, introducing more features to Publiclab.org, etc. I intend to stay around and be a active member for Publiclab.org after the summer is over.

### Commitment


I understand that this is a serious commitment. I don't have any other major commitments and I will devote ~50 hours a week during the entire tenure.


