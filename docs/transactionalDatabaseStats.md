**[CLICK HERE](index.html)** to access the PAMI manual.

#Statistical details of a transactional database

The performance of a mining algorithm primarily depends on the following two key factors: 
1. Distribution of items' frequencies and 
1. Distribution of transaction length

Thus, it is important to know the statistical details of a database. PAMI provides inbuilt classes and functions methods to 
get the statistical details of a database.   In this page, we provide the details of methods to get statistical details from 
a transactional database. 

### Executing transactionalDatabaseStats program

The transactionalDatabaseStats.py program is located in PAMI.extras.dbStats folder. Thus, execute the below lines to run the program.

    #import the program
    import PAMI.extras.dbStats.transactionalDatabaseStats as tds
          
    
    #initialize the program
    obj = tds.transactionalDatabaseStats(inputFile)
    #obj = tds.transactionalDatabaseStats(inputFile,sep=',') #override default tab seperator
    #execute the program
    obj.run()
    
Once the program is executed, users can call different methods to get the statistical details of a database. We now describe the available methods.

#### getDatabaseSize()
    
   This method returns the total number of transactions in a database.  
   
    print(f'Database size : {obj.getDatabaseSize()}')
    
#### getTotalNumberOfItems()

   This method returns the total number of transactions in a database.
   
    print(f'Total number of items : {obj.getTotalNumberOfItems()}')

####.getSparsity()    

   This method returns the sparsity (i.e., the portion of empty values) of the database.
   
    printf(f'Database sparsity : {obj.getSparsity()}')
    
#### getMinimumTransactionLength()

   This method  returns the length of the small transaction in a database. In other words, this function returns the minimum number of items in a transaction.
   
    print(f'Minimum Transaction Size : {obj.getMinimumTransactionLength()}')

#### getAverageTransactionLength()

   This method  returns the length of an average transaction in a database. In other words, this function returns the average number of items in a transaction.
   
    print(f'Average Transaction Size : {obj.getAverageTransactionLength()}')
   
#### getMaximumTransactionLength()
   This method returns the length of the largest transaction in a database. In other words, this function returns the maximum number of items in a transaction. 

    print(f'Maximum Transaction Size : {obj.getMaximumTransactionLength()}')
    
#### getStandardDeviationTransactionLength()
   This method returns the standard deviation of the lengths of transactions in database.

    print(f'Standard Deviation Transaction Size : {obj.getStandardDeviationTransactionLength()}')

#### getVarianceTransactionLength()

   This method returns the variance of the lengths of transactions in a database

    print(f'Variance in Transaction Sizes : {obj.getVarianceTransactionLength()')
    
#### getSparsity():
   This method retuns the sparsity of the database.


#### getSortedListOfItemFrequencies()
   This method returns a sorted dictionary of items and their frequencies in the database. The format of this dictionary is {item:frequency} 
   The items in this dictionary are sorted in frequency descending order. 
   
    itemFrequencies = obj.getSortedListOfItemFrequencies()

#### getTransanctionalLengthDistribution()
   This method returns a sorted dictionary of transaction lengths and their occurrence frequencies in the database. 
   The format of this dictionary is {transactionalLength:frequency}.
   The transaction lengths in this dictionary are sorted in ascending order of their transactional lengths.
   
    transactionLength = obj.getTransanctionalLengthDistribution()
    
#### storeInFile(dictionary, outputFileName)
   This method stores the dictionary in a file. In the output file, the key value pairs of the dictionary are separated by a tab space. 
   
    obj.storeInFile(itemFrequencies, 'itemFrequency.csv')
    obj.storeInFile(transactionLength, 'transactionSize.csv')       
    
    
## Sample code 

    import PAMI.extras.dbStats.transactionalDatabaseStats as tds
          
    print(f'Database size : {obj.getDatabaseSize()}')
    print(f'Total number of items : {obj.getTotalNumberOfItems()}')
    printf(f'Database sparsity : {obj.getSparsity()}')
    print(f'Minimum Transaction Size : {obj.getMinimumTransactionLength()}')
    print(f'Average Transaction Size : {obj.getAverageTransactionLength()}')
    print(f'Maximum Transaction Size : {obj.getMaximumTransactionLength()}')
    print(f'Standard Deviation Transaction Size : {obj.getStandardDeviationTransactionLength()}')
    print(f'Variance in Transaction Sizes : {obj.getVarianceTransactionLength()')
    
    itemFrequencies = obj.getSortedListOfItemFrequencies()
    transactionLength = obj.getTransanctionalLengthDistribution()
    obj.storeInFile(itemFrequencies, 'itemFrequency.csv')
    obj.storeInFile(transactionLength, 'transactionSize.csv')        





