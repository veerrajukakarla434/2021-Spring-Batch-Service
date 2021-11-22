# 2021-Spring-Batch-Service

#### What Is a Batch Job?
* A batch job is a computer program or set of programs processed in batch mode. 
This means that a sequence of commands to be executed by the operating system is listed in a file (often called a batch file, command file, or 
shell script) and submitted for execution as a single unit.
#### OR
* **A batch job reads input data, processes the input data, and writes the processed data to the configured output.**

* The following figure illustrates a simple batch job that fulfills my definition:
![simplebatchjob](https://www.petrikainulainen.net/wp-content/uploads/simplebatchjob.png "simplebatchjob")

* As you can see, this batch job has only one step. This is perfectly fine if your batch job has only one logical task. For example, if you are implementing an import job that reads information from an input file and writes it to the database, your job has only one logical task.

* However, some batch jobs have more than one logical task. For example, you might have to implement a batch job that imports information from an input file and creates an export file that's exported to other applications. In other words, your batch job has two logical tasks. This means that it has two steps as well.
