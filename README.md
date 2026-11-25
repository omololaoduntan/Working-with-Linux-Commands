# Working-with-Linux-Commands
# Working with Linux Commands on AWS

Project Overview

This project documents my hands-on experience working with Linux commands on an Amazon Linux EC2 instance using SSH.

The lab focused on using Linux commands to manage files, organize data, extract information, and process text directly from the terminal.

## Learning Objectives

By completing this lab, I practised how to:

- Use `tee` to direct command output to a file and the terminal.
- Use `sort` to reorganize CSV file contents.
- Use `cut` to extract specific fields from a file.
- Understand the use of `sed` for stream editing.
- Use the pipe operator (`|`) to combine commands.
- Connect to an Amazon Linux EC2 instance using SSH.

## Environment and Tools

- Cloud Provider: Amazon Web Services (AWS)
- Compute Service: Amazon EC2
- Operating System: Amazon Linux
- Connection Method: SSH
- Terminal: Linux Shell
- Commands: `tee`, `sort`, `cut`, `sed`, `grep`, `cat`, `ls`, `pwd`

## Task 1: Connecting to an EC2 Instance Using SSH

I established a secure connection to an Amazon Linux EC2 instance using SSH.


```bash
cd ~/Downloads
chmod 400 labsuser.pem
ssh -i labsuser.pem ec2-user@<public-ip>
```

What I learned:
- SSH provides secure remote access to Linux instances.
- Private key permissions must be properly configured.
- The EC2 public IP address is used to establish the connection.

## Task 2: Using the tee Command

The `tee` command allows output to be displayed in the terminal while simultaneously writing it into a file.

Command:

```bash
hostname | tee file1.txt
```

To confirm that the file was created:

```bash
ls
```

To view the saved content:

```bash
cat file1.txt
```

What I learned:

The `tee` command is useful when I want to view command output and save the same information for future reference or troubleshooting.

## Task 3: Using sort and the Pipe Operator

First, I created a CSV file:

```bash
cat > test.csv
```

I entered the following records:

```text
Factory, 1, Paris
Store, 2, Dubai
Factory, 3, Brasilia
Store, 4, Algiers
Factory, 5, Tokyo
```

I pressed `CTRL + D` to save and exit.

**Sorting the records:

```bash
sort test.csv
```

The command arranged the records alphabetically by their first field.

**Using the pipe operator with grep:

```bash
cat test.csv | grep Paris
```

Expected output:

```text
Factory, 1, Paris
```

**What I learned:

- `sort` helps organize information in files.
- `grep` searches for specific patterns.
- The pipe operator (`|`) passes the output of one command to another.

## Task 4: Using the cut Command

I created a file containing city and state information:

```bash
cat > cities.csv
```

Sample records:

```text
Dallas, Texas
Seattle, Washington
Los Angeles, California
Atlanta, Georgia
New York, New York
```

I used the following command to extract the city names:

```bash
cut -d ',' -f 1 cities.csv
```

Expected output:

```text
Dallas
Seattle
Los Angeles
Atlanta
New York
```

What I learned:

- `-d` specifies the delimiter.
- `-f` specifies the field to extract.
- `cut` is useful for extracting specific columns or fields from structured text.

## Task 5: Understanding the sed Command

The `sed` command is a stream editor used to search, replace, delete, and transform text.

For example, to replace Dallas with Houston in the file:

```bash
sed 's/Dallas/Houston/' cities.csv
```

To save the changes directly to the file:

```bash
sed -i 's/Dallas/Houston/' cities.csv
```

What I learned:

`sed` makes text editing easier and can automate repetitive text-processing operations.

Note: These are additional examples demonstrating the sed objective.*

## Key Takeaways

This lab strengthened my understanding of Linux command-line operations and how different commands can work together.

I learned that:

1. Linux commands can automate repetitive file operations.
2. The pipe operator makes it possible to combine commands.
3. `tee` helps capture and preserve command output.
4. `sort` and `cut` simplify data organization and extraction.
5. `grep` and `sed` are useful for searching and manipulating text.



## Conclusion

This exercise gave me more practical exposure to Linux commands in an AWS cloud environment.

As I continue building my Cloud and DevOps foundation, I am learning that understanding Linux is essential for managing systems, processing information, troubleshooting issues, and automating everyday infrastructure tasks.


#Linux #AWS #CloudComputing #DevOps
