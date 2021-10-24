## CS7IS3 First Assignment: Building a Lucene Retrieval Engine.

**Aditya Kumar Shrivastava, TCD ID: 19323354.**

1. This project implements a search engine using Apache Lucene. 
2. We index and search documents from the cranfiled dataset using Lucene.
3. This search engine is evaluated using trec_eval.

## How to access the azure virtual machine and the repository:
1. Linux VM Public IP Address: 20.105.177.112
2. Connect using a client such as putty and use the .ppk file for authorization,
3. Login as user: azureuser
4. Once logged in, switch user to root using the command: �sudo su ��
5. Type in the command: �whoami� and you should see the output as root.
6. To run the indexer and searcher, switch to the directory containing the assignment code. The name of the
   directory would be �ahsrivas_CS7IS3_Assignment1�. You can type ls to see the directories and then use cd to switch to the above-mentioned directory.
7. Follow the instructions on the readme file

## How to run the project:

**Step 1: Perform a maven clean**

	mvn clean

**Step 2: Download and Install dependencies** 

	mvn install

**Step 3: RunIndexerSearcher the program to index and execute searches on the the cranfield dataset.**

	mvn exec:java -Dexec.mainClass="RunIndexerSearcher"


## Evaluating the search and query results using trex_eval:

Following the generating of the �**results_ashrivas.txt**� file which contains the results of searching on the cranfield dataset, please proceed to evaluate the results using trec_eval. 
**You may do so by running the following command**

	./trec_eval/trec_eval QRelsCorrectedforTRECeval results_ashrivas.txt

**Please note:**
1. When you run the java program 'RunIndexerSearcher.java', the Indexer and Searcher are run with the BM25 similarity score and English Aanlyzer.
   1. This is so because, when the evaluation was carried out using various similarity scoring and analyzers, BM25 and the English Analyzer had the best scores.
   2. To run the retrieval system for different analyzers or similairty socring, please feel free to change the variable name of the analyzer.
      1. For example: presently analyzer = englishAnalyzer. You can just change this line to analyzer = buildCustomAnalyzer;
      2. buildCustomAnalyzer has been created in the Index.java and Searcher.java files and you should be able to update the analyzer seamlessly.
      
2. If you are cloning the repository for the first time on the VM, ensure to run the 'make' command in the trec_ecal direcoty/
   1. If you are not cloning this repository for the first time then trec_eval has been prebuilt on the Virtual Machine and we do not need to run the �make� command
   
3. QRelsCorrectedforTrecEval should be used when you are attempting the evaluate the search results generated by the program.

4. The results folder contains all the results for various combination of analyzers and similarity scoring techniques. Please feel free to run the results in these files with trec eval.
   1. If you want to run the result files in the results.txt files with trec_Eval, you can find all the commands in the file: 'trec_eval_evaluation_commands.txt'
