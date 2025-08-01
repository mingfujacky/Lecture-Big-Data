---
marp: true
theme: default
class: invert
size: 16:9
paginate: true
footer: 國立陽明交通大學 電子與光子學士學位學程
headingDivider: 1
style: |
  section::after {
    content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
  }
  
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns img {
    width: 50%;
  }
  .middle-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .middle-grid img {
    width: 75%;
  }
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .grid img {
    width: 100%;
  }
  .red-text {
    color: red;
  }
  
  .blue-text {
    color: blue;  
  }

  .small-text {
    font-size: 0.50rem;
  }
---
# 巨量資料導論
## Introduction to Big Data Analysis
Instructor: 林志偉 (Jacky Lin)
Material: https://github.com/mingfujacky/Lecture-Big-Data.git
![bg right:20% w:80% Big Data Material in Git](file/image/qrcode_lecture_big_data.png)

# Textbook
![bg right:40% w:70% textbook](file/image/cover_of_introducing_data_science.jpg)
- Introducing Data Science, Davy Cielen, Arno D. B. Meysman, and Mohamed Ali, Manning, 2016
- Big Data: Concepts, Technology, and Architecture, Balamurugan Balusamy, Nandhini Abirami. R, Seifedine Kadry, and Amir H. Gandomi, Wiley, 2021.
- Storytelling with Data, Cole Nussbaumer Knaflic, Wiley, 2015
- 商業智慧, 高昶易, 普林斯頓, 2024.

# Contact Information
- Instructor: 林志偉 jacky.jw.lin@nycu.edu.tw
- TA: 陳宗佑 joey76171.sc13@nycu.edu.tw 

# Course Objectives
- The course introduces students to a broad overview of big data and data science. 
- This course covers a briefing of various topics of big data ecosystem and big data analysis with focus on the open source and cloud-native solutions.

# Instructional Arrangements
- Explain course material and hold hands-on sessions in class (laptop is required).
- Implement examples and assignments in Python.
- Deliver final project in group or individual. The project topic is related to big data or data science.

# Evaluation Criteria
- Attendance(10%): 5 roll calls 
  - 2 points for full attendance
  - 1 point for excused absence (with approved leave)
  - 0 point for unexcused absence
- Homework (30%): 6 assignments will be given (late submissions will not be accepted)
- Mid-term exam (20%): closed-book written exam, covering the first half of the course.
- Final-term exam (20%): closed-book written exam, covering the entire course.
- Project (20%): 
  - (5%)  Progress report oral presentation: Week 9
  - (5%)  Final report oral presentation: Week 15
  - (10%) Submit final written report on E3 by Week 17 (late submissions will not be accepted)

# Course Schedule
[114 1st Semester](https://timetable.nycu.edu.tw/?r=main/crsoutline&Acy=114&Sem=1&CrsNo=520020&lang=)