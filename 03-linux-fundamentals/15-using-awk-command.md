# **Module 3: Linux Fundamentals**  
## **Chapter 15: Using the `awk` Command (Text Processor Commands)**  

---

### **📖 Introduction**  
The `awk` command is a powerful text-processing tool in Linux, ideal for handling structured data and performing complex manipulations. It's particularly useful for working with fields in text files or command output, such as log files or CSV data. In this chapter, we will explore the basic usage of `awk` through examples, and by the end, you will have tasks to practice.

---

## **🔧 The `awk` Command Overview**

### 1. **Basic Syntax of the `awk` Command**  
The basic syntax of `awk` is:

```bash
awk [options] 'pattern {action}' filename
```

- **`pattern`**: This is an optional condition to match specific lines.
- **`action`**: The action to be performed on the lines that match the pattern.

If no pattern is provided, `awk` will process all lines of the file.

---

### 2. **Checking the `awk` Version**  
To verify the version of the `awk` command installed on your system, use the `--version` option:

```bash
awk --version
```

This will display the installed version of `awk`, helping you check compatibility.

---

### 3. **Basic `awk` Usage**

#### 3.1 **Print Specific Fields**  
The most basic use of `awk` is to print specific fields (columns) from a text file. By default, `awk` uses spaces and tabs as field delimiters.

**Example**:  
Suppose you have a file called `data.txt` with the following content:

```bash
John 25 New York
Jane 30 Los Angeles
Jack 35 Chicago
```

To print the first column, use the following `awk` command:

```bash
awk '{print $1}' data.txt
```

**Output**:  
```
John
Jane
Jack
```

This prints the first field of each line.

#### 3.2 **Print Multiple Fields**  
You can print multiple fields by separating them with commas.

**Example**:  
```bash
awk '{print $1, $3}' data.txt
```

**Output**:  
```
John New York
Jane Los Angeles
Jack Chicago
```

This prints the first and third fields from each line.

#### 3.3 **Using Field Separators**  
You can change the field separator using the `-F` option. For example, to process CSV data, you can set the delimiter to a comma.

**Example**:  
Suppose `data.csv` contains:

```bash
name,age,city
John,25,New York
Jane,30,Los Angeles
Jack,35,Chicago
```

To print the second field (age), use the `-F` option to specify a comma as the field separator:

```bash
awk -F, '{print $2}' data.csv
```

**Output**:  
```
age
25
30
35
```

---

### 4. **Using `awk` with Patterns**

#### 4.1 **Pattern Matching**  
You can use `awk` to process only lines that match a certain pattern.

**Example**:  
To print only the lines where the age is greater than 30, use a pattern condition:

```bash
awk '$2 > 30 {print $1, $2}' data.txt
```

**Output**:  
```
Jack 35
```

This prints the name and age of people whose age is greater than 30.

#### 4.2 **Pattern Matching with Regular Expressions**  
You can also use regular expressions for more advanced pattern matching.

**Example**:  
To print the names of people who live in cities starting with "N", use:

```bash
awk '$3 ~ /^N/ {print $1, $3}' data.txt
```

**Output**:  
```
John New York
```

---

### 5. **Performing Actions in `awk`**

#### 5.1 **Calculations with `awk`**  
`awk` can also perform calculations. For example, to calculate the average age from the `data.txt` file:

```bash
awk '{sum += $2} END {print "Average age:", sum/NR}' data.txt
```

**Output**:  
```
Average age: 30
```

This sums the second column (age) and divides it by the number of records (`NR`).

#### 5.2 **String Manipulation**  
You can use `awk` for basic string manipulation. For instance, to print the first letter of each person's name:

```bash
awk '{print substr($1, 1, 1)}' data.txt
```

**Output**:  
```
J
J
J
```

This extracts the first character of each name.

---

### 6. **Working with Piped Output**

You can combine `awk` with other commands using pipes (`|`). For instance, to display the size and name of files in the current directory:

```bash
ls -l | awk '{print $5, $9}'
```

This extracts the file size (column 5) and file name (column 9) from the `ls -l` output.

---

### **📝 Verifying the Output**  
After using `awk`, verify the output by reviewing it or saving it to another file.

**Example**:  
```bash
awk '{print $1}' data.txt > output.txt
cat output.txt
```

This will save the output to a file `output.txt`, and you can review the result.

---

### **⚠️ Important Notes**

- **Field Separators**: The default field separator is whitespace. Use `-F` to specify a custom separator.
- **Patterns and Actions**: Ensure that actions are enclosed in `{}` and patterns are provided without quotes unless using regular expressions.
- **Regular Expressions**: `awk` supports regular expressions, making it a powerful tool for pattern-based text processing.

---

### **🔚 Summary**

In this chapter, we learned how to use the `awk` command to process and manipulate text. We covered basic field extraction, pattern matching, performing calculations, string manipulation, and combining `awk` with other commands. By mastering `awk`, you can handle complex text-processing tasks in Linux.

---
