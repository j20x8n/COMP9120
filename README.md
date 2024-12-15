java c
COMP9120 Database Management Systems 
Assignment 1: Conceptual Modelling  Logical DB Design 
Group assignment (16%) 
Introduction 
The   purpose of this assignment   is to   provide you with experience   in   conceptual   and   relational   database   modelling. You   are given a domain description for the Central   Sydney   Hospital.   There   are   2   high   level   tasks   in this   assignment:
•             Create   an   Entity   Relationship   Diagram   (ERD) that   captures   the   business   concepts   and   requirements   conveyed   in   this description,
•             Translate    your    ER    diagram   into   a   logical   database   design   including   relational   database   schema   creation,   key   constraints and   integrity constraints.
This   is a group assignment for teams   of 3   people   per   group.   You   must   be   enrolled   in   an   assignment   group   on   Canvas.   You   must   inform. the   unit coordinator   if you   have   not formed a group   by the end   of Week   3.
Please also   keep an eye on your email   and   Ed   for   any   announcements   or   posts that   maybe   made.
Submission Details 
The   submission   of   your   solution   is   due   at   11:59pm   on   Sunday   08/09/2024   (Week   6).   You   must   submit   the   items   for   submission (detailed   below) via Canvas.
Items for submission 
Please   submit   your   solution   to   Assignment    1,   in   the   ’Assignment’   section   of   the   unit’s   Canvas   site   by   the   deadline,   including the following four files:
1.          Firstly,   you   should   submit   an   assignment   coversheet   as   a   PDF   document   (.pdf   file   suffix)    which   is   available   for   download fromthis linkon Canvas.
2.          Secondly, you are required   to   submit   your   conceptual   model   in   the   form   of   an   E-R   diagram   using   the   lecture   notation,   formatted   as   a PDF document (.pdf   file suffix). Please justify your choices for entity types, relationship types, attributes, primary keys, constraints and design specialities.
3.          Thirdly, you   should   submit   an   SQL file   (.sql   file   suffix)   containing   all   DDL   statements   necessary   to   fully   instantiate   a working database   based   upon your   ER diagram, and   DML statements to   populate   each   relation. Your file   should   run   without errors   in PostgreSQL   16.2. You can   annotate   your   statements using   ‘   --‘   at the   start of   lines   for comment.   You   should   group   your   statements   for   ease   of   reading   (e.g.   by   keeping   all   table   constraints   within   the   relevant   CREATE TABLE statement rather than declaring them externally,   if   possible).
4.          Lastly, you should   submit   another   pdf document   (.pdf   file   suffix)   including the Relational Model (RM) diagram that   provides   a   visual   model   of your   database   schema.   The   following figure   summarises   the   syntax   you   must   use   for   the   RM diagram:
Domain Description 
The   Central   Sydney   Hospital   (CSH),   one   of   Australia’s   leading   hospitals,   embarked   on   a   major   development   of   an   information systems to deliver improved   healthcare facilities and services   to their   patients.The   CSH   encompasses   four   main   departments:   general,   emergency   department   (ED),   pediatrics,   and   surgery.   Each   department   is   identified   by   a   unique   name   and   may   have   different   daily   operating   hours.   The   general   department   operating   hours   are   10am   to   8pm   daily, whilst   the   emergency   department   is   open   24   hours   a   day. A   department   may   include   wards   which are either   general or specialised   Intensive Care Units (ICUs), where each wardiscomposed of one   or more beds.   Different beds have distinctive comfort levels, dimensions (length and width), and mattress thickness, and   hence   have a different “bed cost” associated with it.   The CSH   has a   pediatrics   department   that   includes   state-of-the-art   wards   and   ICU, and five operating theatres   in addition to   the   seven   within   the   surgery   department.   The   staff   allocation   and   headcount within a department must   be tracked to   assist with future   staffing   requirements.Staff   working   for   the CSH must have their   full name, mobile, address, and salary recorded. A staff can be either a doctor,   nurse,   or   other   allied   health   staff such   as   dietitian,   interpreter,   etc. A   doctor   must   be   qualified   in   at   least   one   medical   specialty   but   not more than five. The   related training date and level   of   proficiency   must   be   kept   to   maintain   compliance.   Some   nurses working with children   must   have a Working with Children Check   (WWCC)   as   a   clearance.   The   clearance   check   is valid for three years and the CSH   monitors the validity to ensure   compliance.All patients treated at the CSH must register their personal information including full   name,   email,   address,   dateofbirth,   mobile, emergency   contact   name and   phone,   and   an   insurance   number.   In the   case   of the   emergency,   upon   arrival,   a   triage nurse assesses the   patient’s conditions to   prioritise treatment   based on severity.   Patients may   also   enter through   other   departments for   a   planned   admission. They   enter through   the   ED   due to   urgent   care   or   critical   conditions.   Other   details   such   as   the   admission   date   and time,   nurse,   and   CSH   d代 写COMP9120 Database Management Systems Assignment 1: Conceptual Modelling & Logical DB DesignSQL
代做程序编程语言octor   involved   should   also   be   recorded.   For   a   planned   admission,   patients   must   specify   the   referring   health   practitioner,   and   a   unique   reference   number   provided   by   the   referring   practitioner.   For an emergency admission,   no   information about a   referring   partitioner   is required.Once   a   patient   is   discharged   on   a   date,   a   billing   statement   is   generated   describing   the   services   provided,   total   cost,   amount   covered   by   insurance,   and   remaining   balance   owed   by   the   patient.   The   patient   receives   an   invoice   for   the   amount   owing, which   can   only   be   paid through   credit   cards. The   credit   card   details   used for   paying the   owing   balance   must   be   recorded   for   accounting   and   reporting.   These   include   the   credit   card   number,   expiry   date,   cardholder   name,   and card verification value (CVV).
Additional details 
In addition to the   model   captured through your   ER diagram, the following details apply:
1.          Fields   in   a tuple   related to   dates   and/or times   should   always   have values.
2.          The   length   and width of   a   bed   should   always   have   values   greater   than   zero,   but   not   exceed   2.13   m   and   1.27   m   respectively. The   mattress thickness   should always   have a value   between   15.24 cm and   17.78   cm.
3.          All attributes   in a   tuple   relating   to details   about   a   name   should   always   have   values.
4.          The staff’s salary   should   always   be   greater than   nil.
5.         Patients   must have a specified email   address.
6.          A   bill should always   have   a   total   cost   of   greater than   nil,   but   not   exceed   $50000.
7.          The owing   balance   and   amount   covered   by   insurance   should   not   be   a   negative value.
Task 1: Entity Relationship Diagram (ERD) 
In   your   first   task,   assume   that   the   CSH   has   recruited   you   as   a   database   designer   to   develop   a   conceptual   model, described   inan   ER diagram, to represent the database design of their   healthcare information   system.
Task 2: Relational Database Design  Modelling 
Your second   task is to design and create a relational database schema based on the Entity   Relationship   Diagram (ERD)   modelled from the first task.   In   particular, your solution should include:
•             A   Relational   Model mapping of the   ERD which describes the   tables   and   attributes with   appropriate   data types   to   capture all   information   in the   model   (please   use the   same   names   as   in   your   ER diagram for   naming tables   and attributes);
•             Creation of the database   schema   using   PostgreSQL   which   include the   appropriate   PRIMARY   KEY,   UNIQUE,   FOREIGN KEY constraints for all   tables;
•             Correct foreign   key specifications   including   ON   DELETE   clauses where   suitable;
•             Appropriate additional integrity   constraints   expressed   by   means   of   NOT   NULL   or   CHECK   clauses;
•             INSERT   statements   to   populate   each   relation   with   at   least   one   record,   to   demonstrate   a   database   instance   consistent with the   ER model.
Escaping PostgreSQL keywords in DDL 
If you   need to escape   PostgreSQL   keywords   like “Table”, you will need to   use double quotes.   e.g. CREATE TABLE “Table” (…);
QA 
Q:   How   to   draw the   link   from   foreign   key   in   a   table   to   its   referenced   candidate   key   in   another   table   if   the   foreign   key   contains   more than one attributes?
A: You should draw it in the same way   to the following RM diagram   (specifically,   see the   Sell table). You can   use   any   of   the available tools such asdraw.io, Visio,Lucidchart, Excalidraw, etc. to draw your diagram.  

Marking 
This assignment is   worth   16% of   your final grade for the unit of study. Your group’s submission will be marked according   to the attached   rubric   (see last section of this   assignment   description).
Group member participation 
If members of your group    do not contribute sufficiently, you should alert the unit coordinator as soon as possible. The course instructor   has the discretion to scale the   group’s   mark for   each   member   as follows:
Percentage of contribution 
Proportion of final grade received 
< 5% contribution 
0% 
5 - 10% contribution 
20% 
11 - 15% contribution 
40% 
16 - 20% contribution 
50% 
21 - 24% contribution 
60% 
25 - 28% contribution 
80% 
29 - 30% contribution 
90% 
> 30% contribution 
100% Note:   The   above   table   assumes   that   each   group   will   have   3   members,   so,   on   average,   around   33%   contribution   is expected   from   each   member   of   the   group.   In   special   case,   if   a   group   has   less   than   3   members   then   the   contribution   percentage    will    be    adjusted    accordingly.   You   must    justify    your   contribution   percentage   by   providing         a    detailed   explanation   of   your   individual   contribution   on   the   assignment   coversheet   mentioned   before.   You   must   also   regularly   record and   maintain a diary of   your group meetings and discussions on Canvas.   Furthermore, we may   run   random face-   to-face   interviews to   understand and   justify your contribution, if needed. 





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
