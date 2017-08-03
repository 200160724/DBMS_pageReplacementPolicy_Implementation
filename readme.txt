CSC 540 - Database Management Systems
Project 2

Team Members:
1. Anuraag Motiwale
2. Abhishek Singh
3. Parag Nakhwa
4. Shriyansh Yadav

The modified files can be found in the “Modified Files” folder.

The simpleDB code with changed files is also included in this submission.

Modfications made to the simpledb files:
Task 1:
1. File Manager Statistics - 


Task 2:
1. Use a Map data structure to keep track of the buffer pool -
Files modified - BasicBufferMgr.java in the simpledb.buffer package.
Added the code to create a HashMap to map the block numbers with the buffer present in the bufferpool.

"// Creating a map for mapping the block number with the buffer
   HashMap<String,Buffer> bufferPoolMap =new HashMap<String,Buffer>();"

The key for HashMap bufferPoolMap is a string given by: block.fileName()+"."+block.number()
The value for HashMap bufferPoolMap is a buffer object containing the corresponding block.  


2. Modify the buffer replacement policy to the Most Recently Modified (MRM) - 
All the changes are made in the BasicBufferMgr.java file.
The original buffer replacement policy of simpledb is naive policy. To change the page replacement policy of simpledb, we added the logic to replace the most recently modified page in the bufferpool inside the following methods: pin, pinNew, flushall. The logic to get the most recently modified buffer to be replaced is written in a new method - chooseMostRecentlyModified().

3. Buffer Manager Statistics - 
