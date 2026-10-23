         ____.  _____  _________  ____  __. ___________________ __________________  ___________ _______   
        |    | /  _  \ \_   ___ \|    |/ _| \_   _____/\_____  \\______   \______ \ \_   _____/ \      \  
        |    |/  /_\  \/    \  \/|      <    |    __)   /   |   \|       _/|    |  \ |    __)_  /   |   \ 
    /\__|    /    |    \     \___|    |  \   |     \   /    |    \    |   \|    `   \|        \/    |    \
    \________\____|__  /\______  /____|__ \  \___  /   \_______  /____|_  /_______  /_______  /\____|__  /
                     \/        \/        \/      \/            \/       \/        \/        \/         \


# Research notice: CarrollPHPStudy

*If you found this page through the `CarrollPHPStudy/1.0` user agent in your logs, this is the notice it points to.*

## How to opt out

**Email jforden@carrollu.edu with your domain and it is removed from measurement within
24 hours.** You don't need to give a reason or prove anything. The removal happens on
the strength of the request alone, before you hear back from us. Asking to be removed
does not affect the study's results in any way that would be reported about you.

If you would rather say no by policy than by email, block the `CarrollPHPStudy/1.0` user
agent at your firewall or WAF. We honour that too: a site that refuses us is recorded as
"not measured", never as "vulnerable".

## What we measure

Carroll University (Waukesha, Wisconsin) is measuring how quickly Wisconsin local and
state government websites on .gov update one piece of software, the PHP scripting
language, after a security fix is published. Minnesota, Illinois, Michigan and Iowa .gov
sites are included for comparison, so the study can say whether Wisconsin's response was
typical. They receive exactly the same single request a day.

We start with the fix released on October 21, 2026 (PHP2Shell, CVE-2026-109618 and
CVE-2026-109619). Site operators are not named or ranked individually. The report is
about groups: what share of town, village, city, county, state, special-district and
election-office sites were already current, and how many updated in the days and weeks
after the fix. Tribal nations' websites are not measured.

To describe how things stood *before* the fix, we also read Common Crawl's public web
archive. That sends no traffic to your site.

## What a request from us looks like

One ordinary request for your homepage over HTTPS, from a tool that identifies itself as
this study. We request `https://yourdomain.gov/` and no other path on your site. If HTTPS
will not connect to your host at all, we make one plain-HTTP attempt, so we can tell
"no site here" from "site here, refusing HTTPS".

- **We never look for vulnerable endpoints and never send an exploit.** The only thing
  we read is what your server volunteers in its normal response headers.
- **We do not test, probe or attack your site.** No port scanning, no guessed paths, no
  form submissions, no logins, no fuzzing, no malformed input.
- **We do not send cookies,** and we do not keep the ones you set, so we cannot follow a
  visitor's session or be logged in as anyone.
- **We read at most the first 64 kilobytes of the homepage**, then discard it. We do not
  store page content, only a few derived yes/no flags.
- **Usually one request per domain per day, and at most three.** An extra request
  happens only when the first one told us nothing:
  - one more if your certificate fails verification. This is a second read without
    verification, purely to tell "unreachable" apart from "reached but showing no
    version";
  - one more if HTTPS cannot connect at all. This is a single plain-HTTP try.

  Three in a day means both of those went wrong.

  Redirects are counted separately. We follow at most three hops within the same site
  on each try. So a site that redirects on every try could see up to twelve requests
  from us in a day, and that only happens on a site that is failing in two ways at once.

  There is never more than one request at a time to the same IP address, and at most 20
  of our requests run at once overall. Each request waits a random 0.1 to 0.5 seconds
  first and has a hard 20-second timeout.
- **How often (planned):** once a day for about two weeks, then on days 21, 28, 45, 60
  and 90 after the fix, then we stop.
- **We identify ourselves.** Every request carries the user agent
  `CarrollPHPStudy/1.0`, the address of this notice
  (`https://github.com/JForden/JForden`) and a contact email, so your security team can
  see exactly who called and why. We never pretend to be a browser.

A broken certificate is recorded as such. A site that returns an error, a refusal (403),
a rate-limit response (429) or a server error (5xx) is not asked again that day.

## What we keep

A small record per domain per day: the domain name, the time, the HTTP status, whether a
PHP version number was visible in the headers, that version string, and which of a few
categories it fell into (up to date with the published fix / older than the fix / no
version visible / not measured). We also keep a log of every request we sent, so that if
anyone asks what we did, we can answer with the record rather than a description.

Everything stays on a university-controlled machine. We publish counts for groups of
sites, and we hide any count smaller than ten. **We do not publish per-site results,
and we do not publish a list of sites that appear vulnerable.**

## Who runs it

Jack Forden, Assistant Professor of Computer Science and AI, Carroll University,
Waukesha, Wisconsin. Email: **jforden@carrollu.edu**. Notice page:
https://github.com/JForden/JForden

Carroll University's IRB has determined that this is not human-subjects research,
because it observes government web servers, not people.

---

# Table of Contents

0. [Research notice and opt-out (CarrollPHPStudy)](#research-notice-carrollphpstudy)

1. [Introduction](#introduction)
2. [What I'm Working On](#what-im-working-on)
3. [Learning](#learning)
4. [Skills](#skills)
   - [Languages & Tools](#languages--tools)
     - [Proficient](#proficient)
     - [Knowledgeable](#knowledgeable)
   - [What I Do](#what-i-do)
   - [Projects](#projects)
   - [Publications](#publications)
5. [Contact Information](#reach-me-at)
6. [Leadership](#leadership)
7. [Awards and Misc](#awards)



# Introduction 


Hello 👋
I'm Jack Forden, I have over 7 years of expertise in **data science**, **AI**, **statistical modeling**, **security measurement**, and **full-stack engineering**. I finished my PhD at **Marquette University** in 2025, I'm passionate about leading innovative projects and cutting-edge research. You can find me helping students at **Carroll University** in Waukesha Wisconsin!

## What I'm Working On:
- I currently Develop and Maintain the research automated assessment system at Marquette and Carroll University, TA-Bot - Check Publications
- Creating an **AI-driven automated grading system** that has processed over 1.17 million API requests  - Check Publications
- Designing frameworks to maximize **student learning** and **academic achievement** - Check Publications
- Building a **passive internet-measurement pipeline** to track how quickly Wisconsin's state and local government websites (with neighbouring states for comparison) patch **PHP2Shell** (CVE-2026-109618 / CVE-2026-109619) - See Projects and the [research notice](#research-notice-carrollphpstudy)

## Learning:  
  - I expect to finish PRSM 2 certification as time allows
  - I am looking forward to starting a course on getting certified in Tableau
  - I am looking forward to finding a course to get certified in Project Management
    

## Skills

### Languages & Tools:

#### Proficient:
- 🐍 Python | 🔗 Flask | ⚛️ React.js | 📈 SQL | 📊 SQLAlchemy | Ollama | Piston

#### Knowledgeable:
- ☕ Java | 🔧 C/C++ | ⚙️ ARM | 🖥️ RISC-V | ☁️ AWS | 📊 R | AI-Modeling | 🔧 TensorFlow | 📊 PyTorch, |  🐳 Docker, DBMS Systems | Tablau | Excel


### What I Do:
- 🌐 **Full-Stack Development**: Flask, React.js, Docker, Microservices, RESTful APIs, AWS, CI/CD pipelines  
- 🛠️ **Low-Level System Design**: Process scheduling, memory management, assembly programming, RTOS development  
- 📊 **Statistical Modeling & Data Science**: Causal inference, A/B testing, hypothesis testing, biostatistics, SQL, R, TensorFlow
- 🤖 **AI & Machine Learning**: LLM evaluation and deployment, NLP, AI decision support systems, open-source LLM integration  
- 🔐 **Security & Internet Measurement**: Passive external reconnaissance, HTTP header and DNS configuration analysis (SPF, DMARC, DKIM, DNSSEC), vulnerability-exposure and patch-adoption measurement, ethical non-intrusive scanning
- 📚 **Education Technology**: Developing frameworks for student engagement and retention, gamification in education

### Projects

- **TA-Bot**: Designed and deployed one of the most flexible assessment systems using Flask, Docker, SQL, SQLAlchemy, Azure Authentication, and React. This has been my main focus as I develop frameworks designed to increase retention rates, and thus tuition. To date, TA-Bot has reduced withdrawal rates in introductory courses at Marquette University by 50%, leading to historic retention rates and an additional $3,000,000 in tuition staying in the CS department. I have published multiple works on this, see publications.  [TA-Bot](https://github.com/JForden/AutoTA)

- **PHP2Shell Patch-Adoption Study** *(in progress)*: A passive measurement study of how fast Wisconsin's state, county, city, town, village and special-district .gov websites patch PHP2Shell, the pair of critical unauthenticated PHP remote-code-execution flaws disclosed in October 2026, with Minnesota, Illinois, Michigan and Iowa for comparison. Tribal nations' sites are not measured. A rate-limited, self-identifying crawler sends one ordinary GET request per domain per day and classifies each site from its advertised PHP version (patched, vulnerable, end-of-life, hidden, or not measured). Results are published only as group counts, never per site. No exploits or intrusive probes are ever sent. Opt out: jforden@carrollu.edu ([notice](#research-notice-carrollphpstudy)).

- Co-developed the first **RISC-V "Mini" OS** under the leadership of [Alex Gebhard](https://github.com/a1g3) for consumer hardware [Github](https://github.com/JForden/riscv-xinu) Read more about it [SIGCSE 2024](https://dl.acm.org/doi/10.1145/3626252.3630959)
- I developed a RISC-V port of the MiniJava Compiler published by [Appel and Jens Palsberg](https://www.amazon.com/Modern-Compiler-Implementation-Andrew-Appel/dp/052182060X). While I would love to share this GitHub repository publicly, I am currently the instructor for Marquette COSC 4400 Compiler Construction, where I am leading students in solving this exact issue! [Publication to appear in SPLASH - JENSFEST](https://2024.splashcon.org/home/jensfest-2024).

- Locally run and hosted AI-Assessment frameworks [ Publication to appear in FIE](https://2024.fie-conference.org/)


#### Side Projects - Unrelated to Research Objectives

- [BA-Hub](https://ba-hub.net/) an online platform that processes and assesses user matches for the online game [Broken Arrow](https://store.steampowered.com/app/1604270/Broken_Arrow/).

The website has 5000 monthly visitors(as of 2025), has processed over 3.5 million multiplayer matches, and has helped produced some [data reports](https://store.steampowered.com/news/app/1604270?emclan=103582791470034480&emgid=824840894153752762) that have shaped the meta of the game itself.            

- A port to the [Piston Code Runner](https://github.com/JForden/piston) augmented to handle Multi-File Java submissions
- A Mobile application developed for [88.9 Milwaukee](https://github.com/JForden/Multi_Media)
- A currated list of most Pylint Errors designed specificlly to help novice students resolve code errors [Github](https://github.com/JForden/pylint-errors)
- Helped to develop and document [competition software](https://github.com/acm-mu/abacus) used in the **largest** HighSchool Programming competition in Wisconsin by thousands of students and hundreds of schools.

### Publications

#### 2025

- **Jack Forden**, Michael Cullen, and Dennis Brylow. 2024. *Paced to Perfection: The Impact of Automated Assessment Rewards for Attending Office Hours*. Research Paper submitted to SIGCSE 2025 on July 15, 2024. Acceptance Notification: September 30, 2024.

- **Jack Forden**, Matthew Schneider, Alexander Gebhard, Md. Tahmidul Islam Molla, and Dennis Brylow. 2024. *Unlocking Student Potential With TA-Bot: Timely Submissions and Improved Code Style*. Research Paper submitted to SIGCSE 2025 on July 15, 2024. Acceptance Notification: September 30, 2024.

#### 2024

- Dennis J. Bouvier, Ellie Lovellette, Eddie Antonio Santos, Brett A. Becker, Tom Crick, Venu G. Dasigi, **Jack Forden**, Olga Glebova, Swaroop Joshi, Stan Kurkovsky, and Seán Russell. 2023. *Teaching Students To Use Programming Error Messages*. In Proceedings of the ACM Conference on Global Computing Education Vol 2 (CompEd 2023), 207–208. Association for Computing Machinery. *To Appear.*

- Samuel B. Mazzone, **Jack Forden**, and Dennis Brylow. 2024. *Exploring the Potential of Locally Run Large Language (AI) Models for Automated Grading in Introductory Computer Science Courses*. Proceedings of the 2024 Frontiers in Education (FIE 2024). Association for Computing Machinery, Washington DC, USA. *To Appear.*

- **Jack Forden**, Alexander Gebhard, Maverick Berner, and Dennis Brylow. 2024. *MiniJava on RISC-V: A Game of Global Compilers Domination*. Proceedings of the Workshop Dedicated to Jens Palsberg on the Occasion of His 60th Birthday (JENSFEST 2024). Association for Computing Machinery, New York, NY, USA. *To Appear.*

- Alexander Gebhard, **Jack Forden**, Oliver Laufenberg, and Dennis Brylow. 2024. *Using Embedded Xinu to Teach Operating Systems on Baremetal RISC-V*. In Proceedings of the 55th ACM Technical Symposium on Computer Science Education V. 1 (SIGCSE 2024). Association for Computing Machinery, New York, NY, USA, 380–386. [https://doi.org/10.1145/3626252.3630959](https://doi.org/10.1145/3626252.3630959)

#### 2023

- Dennis J. Bouvier, Ellie Lovellette, Eddie Antonio Santos, Brett A. Becker, Tom Crick, Venu G. Dasigi, **Jack Forden**, Olga Glebova, Swaroop Joshi, Stan Kurkovsky, and Seán Russell. 2023. *Teaching Students To Use Programming Error Messages*. In Proceedings of the ACM Conference on Global Computing Education Vol 2 (CompEd 2023). Association for Computing Machinery, New York, NY, USA, 207–208. [https://doi.org/10.1145/3617650.3624950](https://doi.org/10.1145/3617650.3624950)

- **Jack Forden**, Alexander Gebhard, and Dennis Brylow. 2023. *Experiences with TA-Bot in CS1*. In Proceedings of the ACM Conference on Global Computing Education Vol 1 (CompEd 2023). Association for Computing Machinery, New York, NY, USA, 57–63. [https://doi.org/10.1145/3576882.3617930](https://doi.org/10.1145/3576882.3617930)

- **Jack Forden**, Alexander Gebhard, and Dennis Brylow. 2023. *Dynamic Rate Limiting with TA-Bot in CS1*. In Proceedings of the 54th ACM Technical Symposium on Computer Science Education V. 2 (SIGCSE 2023). Association for Computing Machinery, New York, NY, USA, 1330. [https://doi.org/10.1145/3545947.3576276](https://doi.org/10.1145/3545947.3576276)


---

📫 **Reach me at**: j.r.forden@gmail.com  
🌐 **LinkedIn**: [LinkedIn Profile](https://www.linkedin.com/in/jack-forden-a1a45920b)  
💻 **GitHub**: [GitHub Profile](https://github.com/JForden)  

### Leadership

#### Vice President | *Association for Computing Machinery (ACM) Marquette* (2022)
- Collaborated with members to enhance programming and networking events.
- Facilitated workshops to help students develop technical skills and industry knowledge.
- Assisted in recruiting new members to grow the ACM chapter.

#### Vice President | *International Honor Society for the Computing and Information Disciplines, Marquette* (2022)
- Promoted academic excellence and community engagement among computing students.
- Organized events to support professional development and networking opportunities.
- Mentored peers in preparing for internships and career opportunities.

#### Executive Board Member | *Sigma Phi Epsilon, Marquette* (2020 -- 2021)
- Contributed to the strategic planning and execution of fraternity events and initiatives.
- Promoted community service and leadership development among members.

#### Executive Board Member | *Multi-Cultural Organization* (2019)
- Facilitated cultural awareness events to promote diversity and inclusion on campus.
- Collaborated with other organizations to enhance community outreach efforts.

#### 1st Place | *Great Lakes Affiliate of College and University Residence Halls Leadership* (2019)
- Recognized for outstanding leadership and contributions to residence hall activities.
- Demonstrated exceptional teamwork and event planning skills during statewide competition.


### Awards

#### Co-author | *US Department of Education GAANN Grant* (2023)
- Co-authored a $600,000 grant supporting advanced educational initiatives in computing.

#### Organizer | *Wisconsin's Largest Student-Run High School Programming Competition* (2023)
- Orchestrated an event involving over 270 high schools across Wisconsin.

#### Dean's List | *Marquette University* (2019 -- Present)
- Consistently recognized for academic excellence throughout my undergraduate studies.

#### Workshop Leader | *Professional Development for Computer Science Educators* (2023)
- Led workshops to enhance teaching strategies for computer science educators.
