"# WhatsUpDocs" 

Pre-Cancun

### Metadata Extravaganza (ME)
### Metadata Experience (ME)
### Metadata Exhibitiion (ME)
### Metadata Examples (ME)


#### OneCallSaul

Gradle plugin to read small SQL definitions in, expand them.  And then to
 use the expanded yaml definitions to generate Java classes based on Freemarker
 templates.

#### SaulDemo

 A demo using the OneCallSaul gradle plugin to actually generate
   Java classes, compile them, and then jar them up under the
   SaulDemo.jar

#### TooSkunk (previous was Skunk - also called JR 'Just Rules')

Took the Skunk/Just Rules project, written in Cancun and did several things ....
* Added Spring SpEL expressions.
* Completely re-factored the input JSON and the executing code.
* Expanded the Rules to have ....
    * Actions
    * Action references
    * Rule references (A rule may reference another rule)

#### TooRest

A rest server that just uses the Data Definition files from SaulDemo
to provide return data packets, based on Rest calls made with the
name of the Data Definition.  Nothing regarding each SQL query returned packet
is hardcoded.  This project has very little code.

#### JrRestScheduler

Uses the TooSkunk project's jar to run Rules defined locally in the src/main/resources/....
  directory.  These rules are run two different ways.  One is on a schedule, a sample rule runs
  every 5 seconds.  And the other is that you can call a Rule as a Rest call, pass it a
  parameter, and have it execute.  Again, not a lot on code in this project.


#### Imagine

 Imagine a code base where much of the day to day code is generated, and programmers
 spend their time adding business logic, not writing simple entities.  Any repeated pattern
 based on Database tables can be generated, jarred, and used by other projects.

 Imagine the ability to track each and every SQL based rest call, the input parameters, and the
 SQL behind the call.  Each SQL definition given a unique name (key) along with a version.  Generated
 pojos assist programmers interacting with each definition, and each call to the database, or Rest
 call logged to a central source with all parameters use in the WHERE clause as a filter.

 Imagine a set of Rules, defined as text in a persistent storage area, that can be jarred, shared,
 run as rest calls, read from persistent storage, etc.  And that have to ability, when executed, to
 report the execution path, along with the data used to get there.

 Imagine Rules, through their Actions, able to access on demand, dynamically, self logging, persisted and/or
 cached data packets based on unique Metadata definition names/keys.  These Rules, of course, are able
 to provide dynamic parameters for each request of a data packet.
