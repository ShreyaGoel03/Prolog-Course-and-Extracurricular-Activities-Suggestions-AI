# Prolog-Course-and-Extracurricular-Activities-Suggestions-
<p align="justify">
Forward Chaining refers to that we are given a set of facts and we try to derive conclusions from these facts. durable-rules refer to defining the event, fact pattern to match and the action to take.
<br/></p>

### Algorithm Design:
<p align="justify">
The overview of the whole system is as follows:<br/>
Given: Interest of the student, grade of the student<br/>
Output: The suggestion list of courses and extracurricular activities<br/>
</p>

#### Process:
<p align="justify">
There is 4 ruleset that is used that is ‘interests’, ‘basic courses’, ‘courses’, ‘activities’.<br/>
1. The student is first asked to enter the current grade as an input which lies
between 1 to 10.<br/>
2. A list of interests related to the courses and a list of interests of non-technical
activities is being displayed to the student, in which the student enters the index
choice which takes the value of it from the stored dictionary.<br/>
<br/>
    Dictionary which stores the mapping of the index with the interest.
interest_dict = {1:'machine learning', 2:'deep learning', 3:'data engineering',
4:'software development', 5:'computer vision', 6:'algorithms', 7:'animation',
8:'speechaudio', 9:'cybersecurity', 10:'wirelesscommunication', 11:'vlsi', 12:'csp',
13:'bio', 14:'psychology' }
<br/>
<br/>
    Dictionary which stores the mapping of the index with the non-technical activity
interest.
extracurricular_dict = {1:'astronomy', 2:'audio', 3:'literature', 4:'theatre', 5:'dance',
6:'standup', 7:'photography', 8:'finance', 9:'art', 10:'fashion'}
<br/>
<br/>
</p>
<p align="justify">
3. After the student has entered valid indexes, then for courses interest, the
‘interests’ ruleset is called and then the matched facts according to the interest
and the grade is being triggered. This is the repeated application of logical
modus ponens to the set of facts being called to derive a conclusion. The basic
courses and core/elective courses ruleset are being called and ‘activities ruleset
which displays the technical club.</p>

<p align="justify">
4. For the non-technical interest choice, the fact calls the ‘activities’ ruleset which
matches the set of facts/events present inside and then calls the set of facts
present inside that matched function.</p>
<br/>

#### How Forward Chaining Displayed: <br/>
<p align="justify">
Since the student is asked the interest of its choice and the fact is generated,
assert_fact('interests', {'interest':interest_value, 'grade':grade}). This fact calls the
‘interests’ ruleset and then matches that is following the logical modus ponens, where p
= initial fact generated above/ matched function with this fact, q = facts written inside the
matched function of ruleset if exists, then it calls q. So, this q is followed by here as
‘basic courses’, then ‘courses’ and then technical ‘activities’. This process repeats to the
sets of facts being called to derive the conclusion. Then, concluding courses facts(goal)
are displayed from all the ruleset. SImilarily for the extracurricular activities, the fact
generated from the user choice is assert_fact('activities', {'club':interest_value_1}). This
fact calls the ‘activities ruleset and then matches that is also following the logical modus
ponens, where p = initial fact generated above/ matched function with this fact, q = facts
written inside the matched function of the ruleset if exists, then it calls q. This process
repeats to the sets of facts being called to derive the conclusion. So, it lists out all the
extracurricular clubs/activities present in IIITD to the student, which is the goal.</p>

#### Modus Ponens:<br/>
p<br/>
If p then q<br/>
--------------<br/>
q<br/>
Hence, this is how forward chaining is shown here, that is given from the set of facts
and we try to derive conclusions from these facts.
<br/>

### Input-Output:
#### Given Input Initial Facts:
assert_fact('interests', {'interest':interest_value, 'grade':grade})<br/>
assert_fact('activities', {'club':interest_value_1})<br/>
Here, interest_value = Course related interest input by student<br/>
Grade = Input grade by user<br/>
interest_value_1 = Extra Curricular related interest input by student<br/>

#### Output:<br/>
Concluding Facts related to the list of courses and extracurricular activities based on
interest.<br/>
For Example, for some valid course interest - ‘algorithms’, grade - 8, and non-technical
interest - ‘finance’.<br/>
<br/>
**Concluding Output obtained facts after Forward Chaining:**<br/>
Fact: Choose Foundation Course - Analysis and Design of Algorithms<br/>
Fact: Choose Foundation Course - Data Structures and Algorithms<br/>
Fact: Choose Elective Course - Introduction to Graduate Algorithms<br/>
Fact: Choose Elective Course - Program Verification and Analysis<br/>
Fact: Choose Elective Course - Algorithms in Computational Biology<br/>
Fact: Choose Elective Course - Randomized Algorithms<br/>
Fact: Choose Elective Course - Modern Algorithm Design<br/>
Fact: Technical Club Foobar:- Competitive Programming Club<br/>
Fact: NonTechnical Club Finnexia:- Finance Club<br/>

#### Screenshots:

![Output1](https://user-images.githubusercontent.com/43794593/154136629-72cb5f5a-dd3f-4af7-8e33-d4d9aa8a0e0e.png)

![Output2](https://user-images.githubusercontent.com/43794593/154136638-2a90214f-56d6-4c28-b178-71568c0b4c21.png)

