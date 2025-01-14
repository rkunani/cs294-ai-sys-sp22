---
layout: default
---


# Machine Learning Systems (Spring 2022)

* **When**: *Mondays from 1:00 to 4:00*
* **Where**: Soda 405 (and on zoom with link posted in Piazza).
* **Instructor**: [Joseph E. Gonzalez](https://eecs.berkeley.edu/~jegonzal)
* **Co-Instructor**: [Amir Gholami](https://eecs.berkeley.edu/~amirgh)
* **Office Hours:**: Arrange by email.
* **Announcements**: [Piazza](piazza.com/berkeley/spring2022/cs294162)
* **Sign-up to Present**: Every student should sign-up to present in at least three rows and as different roles each time.  Note that the Backup/Scribe presenter may be asked to fill in for one of the other roles with little notice.
* If you have reading suggestions please send a pull request to this course website on [Github](https://github.com/ucbrise/cs294-ai-sys-sp22) by modifying the [index.md](https://github.com/ucbrise/cs294-ai-sys-sp22/blob/master/index.md) file.


## Course Description

The recent success of AI has been in large part due in part to advances in hardware and software systems. These systems have enabled training increasingly complex models on ever larger datasets. In the process, these systems have also simplified model development, enabling the rapid growth in the machine learning community. These new hardware and software systems include a new generation of GPUs and hardware accelerators (e.g., TPU and Nervana), open source frameworks such as Theano, TensorFlow, PyTorch, MXNet, Apache Spark, Clipper, Horovod, and Ray, and a myriad of systems deployed internally at companies just to name a few. 
At the same time, we are witnessing a flurry of ML/RL applications to improve hardware and system designs, job scheduling, program synthesis, and circuit layouts.  

In this course, we will describe the latest trends in systems designs to better support the next generation of AI applications, and applications of AI to optimize the architecture and the performance of systems. 
The format of this course will be a mix of lectures, seminar-style discussions, and student presentations. 
Students will be responsible for paper readings, and completing a hands-on project. 
For projects, we will strongly encourage teams that contains both AI and systems students.



## New Course Format

Two previous versions of this course were offered in <a href="https://ucbrise.github.io/cs294-ai-sys-sp19/#today">Spring 2019</a>, and <a href="https://ucbrise.github.io/cs294-ai-sys-fa19/#today">Fall 2019</a>.
The format of this third offering is slightly different.  Each week will cover a different research area in AI-Systems.
The lecture will be organized around a mini program committee meeting for the weeks readings. Students will be required to submit detailed reviews
for a subset of the papers and lead the paper review discussions. For some of the topics, we have also invited prominent researchers for each area and they will present
an overview of the field, followed by discussions raised during the "committee meeting".
The goal of this new format is to both build a mastery of the material and also to
develop a deeper understanding of how to evaluate and review research and hopefully provide insight into how to write better papers. 


## Course Syllabus
{% capture dates %}
1/24/22
{% endcapture %}
{% assign dates = dates | split: " " %}

This is a tentative schedule. Specific readings are subject to change as new material is published.

<a href="#today"> Jump to Today </a>

<table class="table table-striped syllabus">
<thead>
   <tr>
      <th style="width: 5%"> Week </th>
      <th style="width: 10%"> Date </th>
      <th style="width: 85%"> Topic </th>
   </tr>
</thead>
<tbody>


{% include syllabus_entry %}
## Introduction and Course Overview

This lecture will be an overview of the class, requirements, and an introduction to the history of machine learning and systems research. 

* Lecture slides: [[pdf](assets/lectures/lec01/01_ai-sys-intro-small.pdf), [pptx](assets/lectures/lec01/01_ai-sys-intro.pptx)]

<div class="reading">
<div class="required_reading" markdown="1">

* [SysML: The New Frontier of Machine Learning Systems](https://arxiv.org/abs/1904.03257)
* Read Chapter 1 of [_Principles of Computer System Design_](https://www.sciencedirect.com/book/9780123749574/principles-of-computer-system-design). You will need to be on campus or use the Library VPN to obtain a free PDF.
* [A Few Useful Things to Know About Machine Learning](https://homes.cs.washington.edu/~pedrod/papers/cacm12.pdf)

</div>

<div class="optional_reading" markdown="1">
* [How to read a paper](https://web.stanford.edu/class/ee384m/Handouts/HowtoReadPaper.pdf) provides some pretty good advice on how to read papers effectively.
* Timothy Roscoe's [writing reviews for systems conferences](https://people.inf.ethz.ch/troscoe/pubs/review-writing.pdf) will also help you in the reviewing process.
</div>
</div>

</td>
</tr>
</tbody>
</table>

## Projects

Detailed candidate project descriptions will be posted shortly.  However, students are encourage to find projects that relate to their ongoing research.


## Grading

Grades will be largely based on class participation and projects.  In addition, we will require weekly paper summaries submitted before class.
* **Projects:** _60%_
* **Weekly Summaries:** _20%_
* **Class Participation:** _20%_









<script type="text/javascript">


var current_date = new Date();
var rows = document.getElementsByTagName("th");
var finished =  false;
for (var i = 1; i < rows.length && !finished; i++) {
   var r = rows[i];
   if (r.id.startsWith("counter_")) {
      var fields = r.id.split("_")
      var week_div_id = "week_" + fields[2]
      var lecture_date = new Date(fields[1] + " 23:59:00")
      if (current_date <= lecture_date) {
         finished = true;
         r.style.background = "orange"
         r.style.color = "black"
         var week_td = document.getElementById(week_div_id)
         week_td.style.background = "#043361"
         week_td.style.color = "white"
         var anchor = document.createElement("div")
         anchor.setAttribute("id", "today")
         week_td.prepend(anchor)
      }
   }
}

$(".reading").each(function(ind, elem) {
   var optional_reading = $(elem).find(".optional_reading");
   if(optional_reading.length == 1) {
      optional_reading = optional_reading[0];
      optional_reading.setAttribute("id", "optional_reading_" + ind);
      var button = document.createElement("button");
      button.setAttribute("class", "btn btn-primary btn-sm");
      button.setAttribute("type", "button");
      button.setAttribute("data-toggle", "collapse");
      button.setAttribute("data-target", "#optional_reading_" + ind);
      button.setAttribute("aria-expanded", "false");
      button.setAttribute("aria-controls", "#optional_reading_" + ind);
      optional_reading.setAttribute("class", "optional_reading_no_heading collapse")
      button.innerHTML = "Additional Optional Reading";
      optional_reading.before(button)
   }
   
})


$(".details").each(function(ind, elem) {
      elem.setAttribute("id", "details_" + ind);
      var button = document.createElement("button");
      button.setAttribute("class", "btn btn-primary btn-sm");
      button.setAttribute("type", "button");
      button.setAttribute("data-toggle", "collapse");
      button.setAttribute("data-target", "#details_" + ind);
      button.setAttribute("aria-expanded", "false");
      button.setAttribute("aria-controls", "#details_" + ind);
      elem.setAttribute("class", "details_no_heading collapse")
      button.innerHTML = "Detailed Description";
      elem.before(button)
   })

</script>


