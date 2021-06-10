# Inverted-Index-for-Search-Engine
This project creates a simple Inverted Index for a Search Engine in Python

## Corpus
The corpus contains 3495 documents of type HTML. The documents are divided in three sub-directories (1-3).

## TASK 1: Preprocessing:
The first step in creating an index is tokenization. We convert a document into Tokens suitable for indexing. The
tokenizer follows these steps:
1. Accepts a directory name as a input, and processes all files found in that directory
2. Extracts the document text with an HTML parsing library, ignoring the headers at the beginning of the file and all
HTML tags
3. Splits the text into tokens 
4. Converts all tokens to lowercase (this is not always ideal, but indexing intelligently in a case-sensitive manner is
tricky)
5. Applies stop-wording to the document by ignoring any tokens found in this list 
6. Applies stemming to the document using any standard algorithm – KStem stemmers. A stemming library is used for this step.

## TASK 2: Creating Inverted Index:
### Step 1: 
We receive the token in <term, docID, position> form from step2 and create the inverted index in memory using dict in python. The corpus is divided in three subdirectories. Each sub-directory is treated as a block, and an index is created of one block at a time 
### Step 2: 
We Write index to file; The index is written in two files, one file for terms and one file for posting list.

### Posting list:
Posting list contains the df of terms and then documents ID and position of term. It is sorted on basis of docID and further on positon, and converted into gap list using delta encoding.

Step 1 and 2 is repeated for each directory therefore, at the end of this step we have 6 files named as index_1_terms.txt, index_2_terms.txt, index_3_terms.txt, index_1_postings.txt, index_2_postings.txt, index_3_postings.txt where 1, 2, 3 represent the name of subdirectory on which index was created.

## TASK 3: Merging Inverted Indexes:
This step merges the three indexes made in the previous step. Final index is on a file named inverted_index_terms.txt and inverted_index_postings.txt

## TASK 4: Keeping additional Information:
We store a separate file that contains the following information about each document:
docID,sub_directory/documentName,documentLength

## TASK 5: Reading Inverted Indexes:
In this task boolean retrieval is performed. Query is taken as input and then tokenized List of documents containing the query terms are printed, one document file name on each line in ascending lexicographical order in following format Sub_directory/documentName If no result the following is printed:
No result found






