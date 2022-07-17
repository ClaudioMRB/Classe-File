# Classe-File
Java File Class



# Java File Class

The File class is an abstract representation of file and directory pathname. A pathname can be either absolute or relative.

The File class have several methods for working with directories and files such as creating new directories or files, deleting and renaming directories or files, listing the contents of a directory etc.

### Fields

| Modifier | Type   | Field             | Description                                                  |
| :------- | :----- | :---------------- | :----------------------------------------------------------- |
| static   | String | pathSeparator     | It is system-dependent path-separator character, represented as a [string](https://www.javatpoint.com/java-string)for convenience. |
| static   | char   | pathSeparatorChar | It is system-dependent path-separator character.             |
| static   | String | separator         | It is system-dependent default name-separator character, represented as a string for convenience. |
| static   | char   | separatorChar     | It is system-dependent default name-separator character.     |

### [Constructors](https://www.javatpoint.com/java-constructor)

| Constructor                       | Description                                                  |
| :-------------------------------- | :----------------------------------------------------------- |
| File(File parent, String child)   | It creates a new File instance from a parent abstract pathname and a child pathname string. |
| File(String pathname)             | It creates a new File instance by converting the given pathname string into an abstract pathname. |
| File(String parent, String child) | It creates a new File instance from a parent pathname string and a child pathname string. |
| File(URI uri)                     | It creates a new File instance by converting the given file: URI into an abstract pathname. |

### Useful Methods

| Modifier and Type | Method                                       | Description                                                  |
| :---------------- | :------------------------------------------- | :----------------------------------------------------------- |
| static File       | createTempFile(String prefix, String suffix) | It creates an empty file in the default temporary-file directory, using the given prefix and suffix to generate its name. |
| boolean           | createNewFile()                              | It atomically creates a new, empty file named by this abstract pathname if and only if a file with this name does not yet exist. |
| boolean           | canWrite()                                   | It tests whether the application can modify the file denoted by this abstract pathname.String[] |
| boolean           | canExecute()                                 | It tests whether the application can execute the file denoted by this abstract pathname. |
| boolean           | canRead()                                    | It tests whether the application can read the file denoted by this abstract pathname. |
| boolean           | isAbsolute()                                 | It tests whether this abstract pathname is absolute.         |
| boolean           | isDirectory()                                | It tests whether the file denoted by this abstract pathname is a directory. |
| boolean           | isFile()                                     | It tests whether the file denoted by this abstract pathname is a normal file. |
| String            | getName()                                    | It returns the name of the file or directory denoted by this abstract pathname. |
| String            | getParent()                                  | It returns the pathname string of this abstract pathname's parent, or null if this pathname does not name a parent directory. |
| Path              | toPath()                                     | It returns a java.nio.file.Path object constructed from the this abstract path. |
| URI               | toURI()                                      | It constructs a file: URI that represents this abstract pathname. |
| File[]            | listFiles()                                  | It returns an [array](https://www.javatpoint.com/array-in-java)of abstract pathnames denoting the files in the directory denoted by this abstract pathname |
| long              | getFreeSpace()                               | It returns the number of unallocated bytes in the partition named by this abstract path name. |
| String[]          | list(FilenameFilter filter)                  | It returns an array of strings naming the files and directories in the directory denoted by this abstract pathname that satisfy the specified filter. |
| boolean           | mkdir()                                      | It creates the directory named by this abstract pathname.    |

------

## Java File Example 1

1. **import** java.io.*; 
2. **public** **class** FileDemo { 
3.   **public** **static** **void** main(String[] args) { 
4.  
5. ​    **try** { 
6. ​      File file = **new** File("javaFile123.txt"); 
7. ​      **if** (file.createNewFile()) { 
8. ​        System.out.println("New File is created!"); 
9. ​      } **else** { 
10. ​        System.out.println("File already exists."); 
11. ​      } 
12. ​    } **catch** (IOException e) { 
13. ​      e.printStackTrace(); 
14. ​    } 
15.  
16.   } 
17. } 

Output:

```
New File is created!
```

## Java File Example 2

1. **import** java.io.*; 
2. **public** **class** FileDemo2 { 
3.   **public** **static** **void** main(String[] args) { 
4.  
5. ​    String path = ""; 
6. ​    **boolean** bool = **false**; 
7. ​    **try** { 
8. ​      // createing new files 
9. ​      File file = **new** File("testFile1.txt"); 
10. ​      file.createNewFile(); 
11. ​      System.out.println(file); 
12. ​      // createing new canonical from file object 
13. ​      File file2 = file.getCanonicalFile(); 
14. ​      // returns true if the file exists 
15. ​      System.out.println(file2); 
16. ​      bool = file2.exists(); 
17. ​      // returns absolute pathname 
18. ​      path = file2.getAbsolutePath(); 
19. ​      System.out.println(bool); 
20. ​      // if file exists 
21. ​      **if** (bool) { 
22. ​        // prints 
23. ​        System.out.print(path + " Exists? " + bool); 
24. ​      } 
25. ​    } **catch** (Exception e) { 
26. ​      // if any error occurs 
27. ​      e.printStackTrace(); 
28. ​    } 
29.   } 
30. } 

Output:

<iframe marginwidth="0" marginheight="0" frameborder="0" scrolling="no" title="Primis Frame" id="google_ads_iframe_dummy_sekindoParent574" style="background: none 0px 0px / auto repeat scroll padding-box border-box transparent; border: medium none currentcolor; inset: auto; clear: none; clip: auto; color: inherit; counter-increment: none; counter-reset: none; cursor: auto; direction: inherit; display: inline; float: none; font-family: inherit; font-size: inherit; font-style: inherit; font-variant: normal; font-weight: inherit; height: 1px; letter-spacing: normal; line-height: inherit; list-style-type: inherit; list-style-position: outside; list-style-image: none; margin: 0px; max-height: none; max-width: none; min-height: 0px; min-width: 0px; opacity: 1; padding: 0px; position: absolute; quotes: &quot;&quot; &quot;&quot;; table-layout: auto; text-align: inherit; text-decoration: inherit; text-indent: 0px; text-transform: none; unicode-bidi: normal; vertical-align: baseline; visibility: inherit; white-space: normal; width: 1px; word-spacing: normal; z-index: auto; -webkit-border-image: none; border-radius: 0px; box-shadow: none; box-sizing: content-box; columns: auto auto; column-gap: normal; column-rule: medium none black; font-feature-settings: normal; overflow: visible; hyphens: manual; perspective: none; perspective-origin: 50% 50%; backface-visibility: visible; text-shadow: none; transition: all 0s ease 0s; transform: none; transform-origin: 50% 50%; transform-style: flat; word-break: normal;"></iframe>



<iframe src="https://imasdk.googleapis.com/js/core/bridge3.521.0_en.html#goog_884945606" allowfullscreen="" allow="autoplay" id="goog_884945606" width="350" height="197" style="background: none 0px 0px / auto repeat scroll padding-box border-box transparent; border: 0px; inset: auto; clear: none; clip: auto; color: inherit; counter-increment: none; counter-reset: none; cursor: auto; direction: inherit; display: inline; float: none; font-family: inherit; font-size: inherit; font-style: inherit; font-variant: normal; font-weight: inherit; height: 197px; letter-spacing: normal; line-height: inherit; list-style-type: inherit; list-style-position: outside; list-style-image: none; margin: 0px; max-height: none; max-width: none; min-height: 0px; min-width: 0px; opacity: 1; padding: 0px; position: relative; quotes: &quot;&quot; &quot;&quot;; table-layout: auto; text-align: inherit; text-decoration: inherit; text-indent: 0px; text-transform: none; unicode-bidi: normal; vertical-align: baseline; visibility: inherit; white-space: normal; width: 350px; word-spacing: normal; z-index: auto; -webkit-border-image: none; border-radius: 0px; box-shadow: none; box-sizing: content-box; columns: auto auto; column-gap: normal; column-rule: medium none black; font-feature-settings: normal; overflow: visible; hyphens: manual; perspective: none; perspective-origin: 50% 50%; backface-visibility: visible; text-shadow: none; transition: all 0s ease 0s; transform: none; transform-origin: 50% 50%; transform-style: flat; word-break: normal; color-scheme: light;"></iframe>



```
testFile1.txt
/home/Work/Project/File/testFile1.txt
true
/home/Work/Project/File/testFile1.txt Exists? true
```

## Java File Example 3

1. **import** java.io.*; 
2. **public** **class** FileExample { 
3. **public** **static** **void** main(String[] args) { 
4.   File f=**new** File("/Users/sonoojaiswal/Documents"); 
5.   String filenames[]=f.list(); 
6.   **for**(String filename:filenames){ 
7. ​    System.out.println(filename); 
8.   } 
9. } 
10. } 

Output:

```
"info.properties"
"info.properties".rtf
.DS_Store
.localized
Alok news
apache-tomcat-9.0.0.M19
apache-tomcat-9.0.0.M19.tar
bestreturn_org.rtf
BIODATA.pages
BIODATA.pdf
BIODATA.png
struts2jars.zip
workspace
```

## Java File Example 4

1. **import** java.io.*; 
2. **public** **class** FileExample { 
3. **public** **static** **void** main(String[] args) { 
4.   File dir=**new** File("/Users/sonoojaiswal/Documents"); 
5.   File files[]=dir.listFiles(); 
6.   **for**(File file:files){ 
7. ​    System.out.println(file.getName()+" Can Write: "+file.canWrite()+"  
8. ​    Is Hidden: "+file.isHidden()+" Length: "+file.length()+" bytes"); 
9.   } 
10. } 
11. } 

Output:

```
"info.properties" Can Write: true Is Hidden: false Length: 15 bytes
"info.properties".rtf Can Write: true Is Hidden: false Length: 385 bytes
.DS_Store Can Write: true Is Hidden: true Length: 36868 bytes
.localized Can Write: true Is Hidden: true Length: 0 bytes
Alok news Can Write: true Is Hidden: false Length: 850 bytes
apache-tomcat-9.0.0.M19 Can Write: true Is Hidden: false Length: 476 bytes
apache-tomcat-9.0.0.M19.tar Can Write: true Is Hidden: false Length: 13711360 bytes
bestreturn_org.rtf Can Write: true Is Hidden: false Length: 389 bytes
BIODATA.pages Can Write: true Is Hidden: false Length: 707985 bytes
BIODATA.pdf Can Write: true Is Hidden: false Length: 69681 bytes
BIODATA.png Can Write: true Is Hidden: false Length: 282125 bytes
workspace Can Write: true Is Hidden: false Length: 1972 bytes
```

FileDescriptor class serves as an handle to the underlying machine-specific structure representing an open file, an open [socket](https://www.javatpoint.com/socket-programming)

, or another source or sink of bytes. The handle can be err, in or out.



The FileDescriptor class is used to create a [FileInputStream](https://www.javatpoint.com/java-fileinputstream-class)

or [FileOutputStream](https://www.javatpoint.com/java-fileoutputstream-class)to contain it.



### Field

| Modifier | Type           | Field | Description                             |
| :------- | :------------- | :---- | :-------------------------------------- |
| static   | FileDescriptor | err   | A handle to the standard error stream.  |
| static   | FileDescriptor | in    | A handle to the standard input stream.  |
| static   | FileDescriptor | out   | A handle to the standard output stream. |

### Constructors

| Constructor      | Description                                                  |
| :--------------- | :----------------------------------------------------------- |
| FileDescriptor() | Constructs an (invalid) FileDescriptor [object](https://www.javatpoint.com/object-and-class-in-java). |

### Method

| Modifier and Type | Method  | Description                                                  |
| :---------------- | :------ | :----------------------------------------------------------- |
| void              | sync()  | It force all system buffers to synchronize with the underlying device. |
| boolean           | valid() | It tests if this file descriptor object is valid.            |

------

## Java FileDescriptor Example

1. **import** java.io.*; 
2. **public** **class** FileDescriptorExample { 
3.   **public** **static** **void** main(String[] args) { 
4. ​    FileDescriptor fd = **null**; 
5. ​    **byte**[] b = { 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58 }; 
6. ​    **try** { 
7. ​      FileOutputStream fos = **new** FileOutputStream("Record.txt"); 
8. ​      FileInputStream fis = **new** FileInputStream("Record.txt"); 
9. ​      fd = fos.getFD(); 
10. ​      fos.write(b); 
11. ​      fos.flush(); 
12. ​      fd.sync();// confirms data to be written to the disk 
13. ​      **int** value = 0; 
14. ​      // for every available bytes 
15. ​      **while** ((value = fis.read()) != -1) { 
16. ​        **char** c = (**char**) value;// converts bytes to char 
17. ​        System.out.print(c); 
18. ​      } 
19. ​      System.out.println("\nSync() successfully executed!!"); 
20. ​    } **catch** (Exception e) { 
21. ​      e.printStackTrace(); 
22. ​    } 
23.   } 
24. } 

Output:

```
0123456789:
Sync() successfully executed!!
```

Record.txt:



```
0123456789:
```

# Java - RandomAccessFile

This [class](https://www.javatpoint.com/object-class) is used for reading and writing to random access file. A random access file behaves like a large [array](https://www.javatpoint.com/array-in-java) of bytes. There is a cursor implied to the array called file [pointer](https://www.javatpoint.com/c-pointers), by moving the cursor we do the read write operations. If end-of-file is reached before the desired number of byte has been read than EOFException is [thrown](https://www.javatpoint.com/throw-keyword). It is a type of IOException.

### Constructor

| [Constructor](https://www.javatpoint.com/java-constructor)   | Description                                                  |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| RandomAccessFile(File file, [String](https://www.javatpoint.com/java-string) mode) | Creates a random access file stream to read from, and optionally to write to, the file specified by the File argument. |
| RandomAccessFile(String name, String mode)                   | Creates a random access file stream to read from, and optionally to write to, a file with the specified name. |

### Method

| Modifier and Type | Method                | Method                                                       |
| :---------------- | :-------------------- | :----------------------------------------------------------- |
| void              | close()               | It closes this random access file stream and releases any system resources associated with the stream. |
| FileChannel       | getChannel()          | It returns the unique [FileChannel](https://www.javatpoint.com/data-transfer-between-channels) object associated with this file. |
| int               | readInt()             | It reads a signed 32-bit integer from this file.             |
| String            | readUTF()             | It reads in a string from this file.                         |
| void              | seek(long pos)        | It sets the file-pointer offset, measured from the beginning of this file, at which the next read or write occurs. |
| void              | writeDouble(double v) | It converts the double argument to a long using the doubleToLongBits method in class Double, and then writes that long value to the file as an eight-byte quantity, high byte first. |
| void              | writeFloat(float v)   | It converts the float argument to an int using the floatToIntBits method in class Float, and then writes that int value to the file as a four-byte quantity, high byte first. |
| void              | write(int b)          | It writes the specified byte to this file.                   |
| int               | read()                | It reads a byte of data from this file.                      |
| long              | length()              | It returns the length of this file.                          |
| void              | seek(long pos)        | It sets the file-pointer offset, measured from the beginning of this file, at which the next read or write occurs. |

------

## Example

1. **import** java.io.IOException; 
2. **import** java.io.RandomAccessFile; 
3.  
4. **public** **class** RandomAccessFileExample { 
5.   **static** **final** String FILEPATH ="myFile.TXT"; 
6.   **public** **static** **void** main(String[] args) { 
7. ​    **try** { 
8. ​      System.out.println(**new** String(readFromFile(FILEPATH, 0, 18))); 
9. ​      writeToFile(FILEPATH, "I love my country and my people", 31); 
10. ​    } **catch** (IOException e) { 
11. ​      e.printStackTrace(); 
12. ​    } 
13.   } 
14.   **private** **static** **byte**[] readFromFile(String filePath, **int** position, **int** size) 
15. ​      **throws** IOException { 
16. ​    RandomAccessFile file = **new** RandomAccessFile(filePath, "r"); 
17. ​    file.seek(position); 
18. ​    **byte**[] bytes = **new** **byte**[size]; 
19. ​    file.read(bytes); 
20. ​    file.close(); 
21. ​    **return** bytes; 
22.   } 
23.   **private** **static** **void** writeToFile(String filePath, String data, **int** position) 
24. ​      **throws** IOException { 
25. ​    RandomAccessFile file = **new** RandomAccessFile(filePath, "rw"); 
26. ​    file.seek(position); 
27. ​    file.write(data.getBytes()); 
28. ​    file.close(); 
29.   } 
30. } 

The myFile.TXT contains text "This class is used for reading and writing to random access file."

after running the program it will contains

This class is used for reading I love my country and my peoplele.



# Java Scanner

Scanner class in Java is found in the java.util package. Java provides various ways to read input from the keyboard, the java.util.Scanner class is one of them.

The Java Scanner class breaks the input into tokens using a delimiter which is whitespace by default. It provides many methods to read and parse various primitive values.

The Java Scanner class is widely used to parse text for strings and primitive types using a regular expression. It is the simplest way to get input in Java. By the help of Scanner in Java, we can get input from the user in primitive types such as int, long, double, byte, float, short, etc.

The Java Scanner class extends Object class and implements Iterator and Closeable interfaces.



The Java Scanner class provides nextXXX() methods to return the type of value such as nextInt(), nextByte(), nextShort(), next(), nextLine(), nextDouble(), nextFloat(), nextBoolean(), etc. To get a single character from the scanner, you can call next().charAt(0) method which returns a single character.

## Java Scanner Class Declaration

1. **public** **final** **class** Scanner 
2. ​     **extends** Object 
3. ​     **implements** Iterator<String>  

## How to get Java Scanner

To get the instance of Java Scanner which reads input from the user, we need to pass the input stream (System.in) in the constructor of Scanner class. For Example:

1. Scanner in = **new** Scanner(System.in); 

To get the instance of Java Scanner which parses the strings, we need to pass the strings in the constructor of Scanner class. For Example:

1. Scanner in = **new** Scanner("Hello Javatpoint"); 

## Java Scanner Class Constructors

| SN   | Constructor                                             | Description                                                  |
| :--- | :------------------------------------------------------ | :----------------------------------------------------------- |
| 1)   | Scanner(File source)                                    | It constructs a new Scanner that produces values scanned from the specified file. |
| 2)   | Scanner(File source, String charsetName)                | It constructs a new Scanner that produces values scanned from the specified file. |
| 3)   | Scanner(InputStream source)                             | It constructs a new Scanner that produces values scanned from the specified input stream. |
| 4)   | Scanner(InputStream source, String charsetName)         | It constructs a new Scanner that produces values scanned from the specified input stream. |
| 5)   | Scanner(Readable source)                                | It constructs a new Scanner that produces values scanned from the specified source. |
| 6)   | Scanner(String source)                                  | It constructs a new Scanner that produces values scanned from the specified string. |
| 7)   | Scanner(ReadableByteChannel source)                     | It constructs a new Scanner that produces values scanned from the specified channel. |
| 8)   | Scanner(ReadableByteChannel source, String charsetName) | It constructs a new Scanner that produces values scanned from the specified channel. |
| 9)   | Scanner(Path source)                                    | It constructs a new Scanner that produces values scanned from the specified file. |
| 10)  | Scanner(Path source, String charsetName)                | It constructs a new Scanner that produces values scanned from the specified file. |

------

## Java Scanner Class Methods

The following are the list of Scanner methods:

| SN   | Modifier & Type     | Method                                                       | Description                                                  |
| :--- | :------------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 1)   | void                | [close()](https://www.javatpoint.com/post/java-scanner-close-method) | It is used to close this scanner.                            |
| 2)   | pattern             | [delimiter()](https://www.javatpoint.com/post/java-scanner-delimiter-method) | It is used to get the Pattern which the Scanner class is currently using to match delimiters. |
| 3)   | Stream<MatchResult> | findAll()                                                    | It is used to find a stream of match results that match the provided pattern string. |
| 4)   | String              | [findInLine()](https://www.javatpoint.com/post/java-scanner-findinline-method) | It is used to find the next occurrence of a pattern constructed from the specified string, ignoring delimiters. |
| 5)   | string              | [findWithinHorizon()](https://www.javatpoint.com/post/java-scanner-findwithinhorizon-method) | It is used to find the next occurrence of a pattern constructed from the specified string, ignoring delimiters. |
| 6)   | boolean             | [hasNext()](https://www.javatpoint.com/post/java-scanner-hasnext-method) | It returns true if this scanner has another token in its input. |
| 7)   | boolean             | [hasNextBigDecimal()](https://www.javatpoint.com/post/java-scanner-hasnextbigdecimal-method) | It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextBigDecimal() method or not. |
| 8)   | boolean             | [hasNextBigInteger()](https://www.javatpoint.com/post/java-scanner-hasnextbiginteger-method) | It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextBigDecimal() method or not. |
| 9)   | boolean             | [hasNextBoolean()](https://www.javatpoint.com/post/java-scanner-hasnextboolean-method) | It is used to check if the next token in this scanner's input can be interpreted as a Boolean using the nextBoolean() method or not. |
| 10)  | boolean             | [hasNextByte()](https://www.javatpoint.com/post/java-scanner-hasnextbyte-method) | It is used to check if the next token in this scanner's input can be interpreted as a Byte using the nextBigDecimal() method or not. |
| 11)  | boolean             | [hasNextDouble()](https://www.javatpoint.com/post/java-scanner-hasnextdouble-method) | It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextByte() method or not. |
| 12)  | boolean             | [hasNextFloat()](https://www.javatpoint.com/post/java-scanner-hasnextfloat-method) | It is used to check if the next token in this scanner's input can be interpreted as a Float using the nextFloat() method or not. |
| 13)  | boolean             | [hasNextInt()](https://www.javatpoint.com/post/java-scanner-hasnextint-method) | It is used to check if the next token in this scanner's input can be interpreted as an int using the nextInt() method or not. |
| 14)  | boolean             | [hasNextLine()](https://www.javatpoint.com/post/java-scanner-hasnextline-method) | It is used to check if there is another line in the input of this scanner or not. |
| 15)  | boolean             | [hasNextLong()](https://www.javatpoint.com/post/java-scanner-hasnextlong-method) | It is used to check if the next token in this scanner's input can be interpreted as a Long using the nextLong() method or not. |
| 16)  | boolean             | [hasNextShort()](https://www.javatpoint.com/post/java-scanner-hasnextshort-method) | It is used to check if the next token in this scanner's input can be interpreted as a Short using the nextShort() method or not. |
| 17)  | IOException         | [ioException()](https://www.javatpoint.com/post/java-scanner-ioexception-method) | It is used to get the IOException last thrown by this Scanner's readable. |
| 18)  | Locale              | [locale()](https://www.javatpoint.com/post/java-scanner-locale-method) | It is used to get a Locale of the Scanner class.             |
| 19)  | MatchResult         | [match()](https://www.javatpoint.com/post/java-scanner-match-method) | It is used to get the match result of the last scanning operation performed by this scanner. |
| 20)  | String              | [next()](https://www.javatpoint.com/post/java-scanner-next-method) | It is used to get the next complete token from the scanner which is in use. |
| 21)  | BigDecimal          | [nextBigDecimal()](https://www.javatpoint.com/post/java-scanner-nextbigdecimal-method) | It scans the next token of the input as a BigDecimal.        |
| 22)  | BigInteger          | [nextBigInteger()](https://www.javatpoint.com/post/java-scanner-nextbiginteger-method) | It scans the next token of the input as a BigInteger.        |
| 23)  | boolean             | [nextBoolean()](https://www.javatpoint.com/post/java-scanner-nextboolean-method) | It scans the next token of the input into a boolean value and returns that value. |
| 24)  | byte                | [nextByte()](https://www.javatpoint.com/post/java-scanner-nextbyte-method) | It scans the next token of the input as a byte.              |
| 25)  | double              | [nextDouble()](https://www.javatpoint.com/post/java-scanner-nextdouble-method) | It scans the next token of the input as a double.            |
| 26)  | float               | [nextFloat()](https://www.javatpoint.com/post/java-scanner-nextfloat-method) | It scans the next token of the input as a float.             |
| 27)  | int                 | [nextInt()](https://www.javatpoint.com/post/java-scanner-nextint-method) | It scans the next token of the input as an Int.              |
| 28)  | String              | [nextLine()](https://www.javatpoint.com/post/java-scanner-nextline-method) | It is used to get the input string that was skipped of the Scanner object. |
| 29)  | long                | [nextLong()](https://www.javatpoint.com/post/java-scanner-nextlong-method) | It scans the next token of the input as a long.              |
| 30)  | short               | [nextShort()](https://www.javatpoint.com/post/java-scanner-nextshort-method) | It scans the next token of the input as a short.             |
| 31)  | int                 | [radix()](https://www.javatpoint.com/post/java-scanner-radix-method) | It is used to get the default radix of the Scanner use.      |
| 32)  | void                | [remove()](https://www.javatpoint.com/post/java-scanner-remove-method) | It is used when remove operation is not supported by this implementation of Iterator. |
| 33)  | Scanner             | [reset()](https://www.javatpoint.com/post/java-scanner-reset-method) | It is used to reset the Scanner which is in use.             |
| 34)  | Scanner             | [skip()](https://www.javatpoint.com/post/java-scanner-skip-method) | It skips input that matches the specified pattern, ignoring delimiters |
| 35)  | Stream<String>      | [tokens()](https://www.javatpoint.com/post/java-scanner-tokens-method) | It is used to get a stream of delimiter-separated tokens from the Scanner object which is in use. |
| 36)  | String              | [toString()](https://www.javatpoint.com/post/java-scanner-tostring-method) | It is used to get the string representation of Scanner using. |
| 37)  | Scanner             | [useDelimiter()](https://www.javatpoint.com/post/java-scanner-usedelimiter-method) | It is used to set the delimiting pattern of the Scanner which is in use to the specified pattern. |
| 38)  | Scanner             | [useLocale()](https://www.javatpoint.com/post/java-scanner-uselocale-method) | It is used to sets this scanner's locale object to the specified locale. |
| 39)  | Scanner             | [useRadix()](https://www.javatpoint.com/post/java-scanner-useradix-method) | It is used to set the default radix of the Scanner which is in use to the specified radix. |

------

## Example 1

Let's see a simple example of Java Scanner where we are getting a single input from the user. Here, we are asking for a string through in.nextLine() method.

1. **import** java.util.*; 
2. **public** **class** ScannerExample { 
3. **public** **static** **void** main(String args[]){ 
4. ​     Scanner in = **new** Scanner(System.in); 
5. ​     System.out.print("Enter your name: "); 
6. ​     String name = in.nextLine(); 
7. ​     System.out.println("Name is: " + name);       
8. ​     in.close();       
9. ​     } 
10. } 

**Output:**

```
Enter your name: sonoo jaiswal
Name is: sonoo jaiswal
```

## Example 2

1. **import** java.util.*; 
2. **public** **class** ScannerClassExample1 {  
3.    **public** **static** **void** main(String args[]){            
4. ​     String s = "Hello, This is JavaTpoint."; 
5. ​     //Create scanner Object and pass string in it 
6. ​     Scanner scan = **new** Scanner(s); 
7. ​     //Check if the scanner has a token 
8. ​     System.out.println("Boolean Result: " + scan.hasNext()); 
9. ​     //Print the string 
10. ​     System.out.println("String: " +scan.nextLine()); 
11. ​     scan.close();      
12. ​     System.out.println("--------Enter Your Details-------- "); 
13. ​     Scanner in = **new** Scanner(System.in); 
14. ​     System.out.print("Enter your name: ");  
15. ​     String name = in.next();  
16. ​     System.out.println("Name: " + name);      
17. ​     System.out.print("Enter your age: "); 
18. ​     **int** i = in.nextInt(); 
19. ​     System.out.println("Age: " + i); 
20. ​     System.out.print("Enter your salary: "); 
21. ​     **double** d = in.nextDouble(); 
22. ​     System.out.println("Salary: " + d);     
23. ​     in.close();      
24. ​     }  
25. } 

**Output:**

```
Boolean Result: true
String: Hello, This is JavaTpoint.
-------Enter Your Details--------- 
Enter your name: Abhishek
Name: Abhishek
Enter your age: 23
Age: 23
Enter your salary: 25000
Salary: 25000.0
```

## Example 3

1. **import** java.util.*; 
2. **public** **class** ScannerClassExample2 {  
3.    **public** **static** **void** main(String args[]){            
4. ​     String str = "Hello/This is JavaTpoint/My name is Abhishek."; 
5. ​     //Create scanner with the specified String Object 
6. ​     Scanner scanner = **new** Scanner(str); 
7. ​     System.out.println("Boolean Result: "+scanner.hasNextBoolean());      
8. ​     //Change the delimiter of this scanner 
9. ​     scanner.useDelimiter("/"); 
10. ​     //Printing the tokenized Strings 
11. ​     System.out.println("---Tokenizes String---");  
12. ​    **while**(scanner.hasNext()){ 
13. ​      System.out.println(scanner.next()); 
14. ​    } 
15. ​     //Display the new delimiter 
16. ​     System.out.println("Delimiter used: " +scanner.delimiter());      
17. ​     scanner.close(); 
18. ​     }  
19. } 

**Output:**



```
Boolean Result: false
---Tokenizes String---
Hello
This is JavaTpoint
My name is Abhishek.
Delimiter used: /
```

# java.io.PrintStream class

The PrintStream class provides methods to write data to another stream. The PrintStream class automatically flushes the data so there is no need to call flush() method. Moreover, its methods don't throw IOException.

### Commonly used methods of PrintStream class

There are many methods in PrintStream class. Let's see commonly used methods of PrintStream class:

**public void print(boolean b):** it prints the specified boolean value.

**public void print(char c):** it prints the specified char value.

**public void print(char[] c):** it prints the specified character array values.

**public void print(int i):** it prints the specified int value.

**public void print(long l):** it prints the specified long value.

**public void print(float f):** it prints the specified float value.

**public void print(double d):** it prints the specified double value

.**public void print(String s):** it prints the specified string value.

**public void print(Object obj):** it prints the specified object value.

**public void println(boolean b):** it prints the specified boolean value and terminates the line.

**public void println(char c):** it prints the specified char value and terminates the line.

**public void println(char[] c):** it prints the specified character array values and terminates the line.

**public void println(int i):** it prints the specified int value and terminates the line.

**public void println(long l):** it prints the specified long value and terminates the line.

**public void println(float f):** it prints the specified float value and terminates the line.

**public void println(double d):** it prints the specified double value and terminates the line.

**public void println(String s):** it prints the specified string value and terminates the line./li>

**public void println(Object obj):** it prints the specified object value and terminates the line.

**public void println():** it terminates the line only.

**public void printf(Object format, Object... args):** it writes the formatted string to the current stream.

**public void printf(Locale l, Object format, Object... args):** it writes the formatted string to the current stream.

**public void format(Object format, Object... args):** it writes the formatted string to the current stream using specified format.

**public void format(Locale l, Object format, Object... args):** it writes the formatted string to the current stream using specified format.

------



### Example of java.io.PrintStream class

In this example, we are simply printing integer and string values.

1. **import** java.io.*; 
2. **class** PrintStreamTest{ 
3.  **public** **static** **void** main(String args[])**throws** Exception{ 
4.   FileOutputStream fout=**new** FileOutputStream("mfile.txt"); 
5.   PrintStream pout=**new** PrintStream(fout); 
6.   pout.println(1900); 
7.   pout.println("Hello Java"); 
8.   pout.println("Welcome to Java"); 
9.   pout.close(); 
10.   fout.close(); 
11.  } 
12. }  

[download this PrintStream example](https://static.javatpoint.com/src/io/printstream1.zip)

------

### Example of printf() method of java.io.PrintStream class:

Let's see the simple example of printing integer value by format specifier.

1. **class** PrintStreamTest{ 
2.  **public** **static** **void** main(String args[]){ 
3.   **int** a=10; 
4.   System.out.printf("%d",a);//Note, out is the object of PrintStream class 
5.    
6.  } 
7. }  

```
Output:10
```

.
