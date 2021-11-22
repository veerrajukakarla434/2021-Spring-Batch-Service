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

* It seems that I have to rewrite my definition. The final version is:

* **A batch job consists of one or more steps. Each step is responsible of completing one logical task. Every step reads input data, processes the input data, and writes the processed data to the configured output. If the batch job has more than one step, the output of a step is often used as an input of the next step.**

* The following figure illustrates a batch job that has two steps:
![batchjobwithmultiplesteps](https://www.petrikainulainen.net/wp-content/uploads/batchjobwithmultiplesteps.png "batchjobwithmultiplesteps")

#### How Can Spring Batch Help Us?

 * Spring Batch solves all problems. It provides the following features that helps you to solve these problems:
 
 * It helps you to structure your code in a clean way by providing the infrastructure that's used to implement, configure, and run batch jobs.

* It uses so called chunk oriented processing where items are processed one by one and the transaction is committed when the chunk size is met. In other words, it provides you an easy way to manage the size of your transactions.

* It provides proper error handling. For example, you can skip items if an exception is thrown and configure retry logic that's used to determine whether your batch job should retry the failed operation. You can also configure the logic that's used to decide if your transaction should be rolled back. 

* It writes comprehensive log to the used database. This log contains the metadata of each job and step execution, and it's extremely useful if you have to troubleshoot a failed batch job. Because the log is written to a database, you can access it by using a database client.


