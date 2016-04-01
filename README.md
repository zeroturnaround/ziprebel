![ZipRebel logo](http://zeroturnaround.com/wp-content/uploads/2015/03/ZipRebel-640x175.png)

ZipRebel is a file compression tool that is so powerful it can reduce the entire internet to less than a byte of data. Here's a more detailed [announcement](http://zeroturnaround.com/blog/ziprebel-download-the-internet-in-milliseconds/).

## How to use it?

The easiest way is just to call the right method on the ZipRebel class, appropriately called "compress":
```java
long result = new ZipRebel().compress(new byte[] { 1, 1, 1, 1, 1, 1, 1, 1 });
```

Alternatively, ZipRebel can work with Paths and either provide you with result on the Java code level, or conveniently write it to the filesystem near the original file. 

```java
Path original = Paths.get("/etc/passwd");
long result = new ZipRebel().compress(original);
```

or 
```java 
Path original = ...;
Path target = new ZipRebel().compressAndDump(original);
System.out.println(target.toAbsolutePath());
```

## Tests?
We have tested ZipRebel many times.

| File description         | Initial size                       | Final size                    |
---------------------------|------------------------------------|-------------------------------- 
| 01011001                 | example (1 byte)                   |	example.ZR (1 bit)            |
| Jenkins CI	             | jenkins.war (53.9 MB)              |	jenkins.ZR (1 bit)            |
| JIRA	                   | atlassian-jira-6.4.tar.gz (227 MB) |	atlassian-jira-6.4.ZR (1 bit) |


