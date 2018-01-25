# Introduction to Azure Data Lake Store and Analytics
This file contains text you can copy and paste for the examples in Cloud Academy's _Introduction to Azure Data Lake Store and Analytics_ course.  

### Introduction
[Azure Free Trial](https://azure.microsoft.com/free) 

### Processing
```
@searchlog = 
    EXTRACT UserId          int, 
            TimeStamp       DateTime, 
            Language        string, 
            Query           string, 
            Duration        int, 
            Urls            string, 
            ClickedUrls     string
    FROM "/SearchLog.tsv"
    USING Extractors.Tsv();

@out = 
    SELECT TimeStamp, Query
    FROM @searchlog
    WHERE Language == "en-gb";

OUTPUT @out 
    TO "/SearchLog_output.tsv"
    USING Outputters.Tsv();
```

### Conclusion
[Azure Data Lake Store documentation](https://docs.microsoft.com/azure/data-lake-store)  
[Azure Data Lake Analytics documentation](https://docs.microsoft.com/azure/data-lake-analytics)  
support@cloudacademy.com
