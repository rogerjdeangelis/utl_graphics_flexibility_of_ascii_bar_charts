# utl_graphics_flexibility_of_ascii_bar_charts
Graphics flexibility of ascii bar charts.  Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.

    Graphics flexibility of ascii bar charts

     Ascii bar charts are underused?
     They can be easily edited and enhanced.

     Problem: Create and annotate an ascii vertical bar chart

     see github
     https://tinyurl.com/yc2ldda4
     https://github.com/rogerjdeangelis/utl_graphics_flexibility_of_ascii_bar_charts

     SAS Forum
     https://communities.sas.com/t5/Graphics-Programming/Bar-Chart/m-p/489544

    INPUT
    =====

     WORK.HAVE total obs=4

        PERSON      TYPE        VALUE

        Wendye    Talk Time    116.395
        Wendye    Acw Time     290.488
        Johny     Talk Time     86.667
        Johny     Acw Time      20.333


     EXAMPLE OUTPUT
     --------------

                     Presenters Talk Time

    300 +---------------------------------------------------+ 300
        |                290     Wendye Talk Time   20.333  |
        |               *****    Johny  Acw Time   290.488  |
        |               *****    Wendye Acw Time    86.667  |
        |               *****    Johny  Talk Time  116.395  |
    250 +---------------*****-------------------------------+ 250
        |               *****                               |
        |               *****                               |
        |               *****                               |
        |               *****                               |
    200 +---------------*****-------------------------------+ 200
        |               *****                               |
        |               *****                               |
        |               *****                               |
        |               *****                               |
    150 +---------------*****-------------------------------+ 150
        |               *****                               |
        |               *****                     116       |
        |               *****                    *****      |
        |               *****                    *****      |
    100 +---------------*****--------------------*****------+ 100
        |               *****            86      *****      |
        |               *****          *****     *****      |
        |               *****          *****     *****      |
        |               *****          *****     *****      |
     50 +---------------*****----------*****-----*****------+  50
        |               *****          *****     *****      |
        |      20       *****          *****     *****      |
        |     *****     *****          *****     *****      |
        |     *****     *****          *****     *****      |   0
      0 -----------------------------------------------------
              Johny    Wendye          Johny    Wendye
              |-- Acw Time -|          |- Talk Time -|


    PROCESS
    =======


    options ls=64;
    PROC CHART DATA=have;
    title "Presentes Talk Time";
      VBAR person /
      SUMVAR=value
      GROUP=type
      REF=0 to 300 by 50
      AXIS=0 to 300 by 50
      nolegend
    ;
    run;quit;

    Then we edit the result (see below)


    OUTPUT
    ======

    Presentes Talk Time

    VALUE Sum

    300 +---------------------------------------------------------
        |               *****
        |               *****
        |               *****
        |               *****
    250 +---------------*****-------------------------------------
        |               *****
        |               *****
        |               *****
        |               *****
    200 +---------------*****-------------------------------------
        |               *****
        |               *****
        |               *****
        |               *****
    150 +---------------*****-------------------------------------
        |               *****
        |               *****
        |               *****                    *****
        |               *****                    *****
    100 +---------------*****--------------------*****------------
        |               *****          *****     *****
        |               *****          *****     *****
        |               *****          *****     *****
        |               *****          *****     *****
     50 +---------------*****----------*****-----*****------------
        |               *****          *****     *****
        |               *****          *****     *****
        |     *****     *****          *****     *****
        |     *****     *****          *****     *****
        ----------------------------------------------------------
              Johny    Wendye          Johny    Wendye      PERSON

              |-- Acw Time -|          |- Talk Time -|      TYPE


     *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

    data have;
    informat person type $20. value commax20.;
    input person type & value;
    cards4;
    Wendye Talk Time  116,3953488
    Wendye Acw Time  290,4883721
    Johny Talk Time  86,66666667
    Johny Acw Time  20,333333333
    ;;;;
    run;quit;

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

    see process for intial code;

    Next

      Highlight and copy the left axis, then paste on the right
      Highlight tict values on left axis, then paste on the right

      Print input data and copy and paste actual data into graph.



