# Proposal 1: Smart Backup Using Link

## Introduction

To get reliable storage, most existing designs are based on ACID properties (Atomicity, Consistency, Isolation and Durability). However, some files are so important that we cannot afford to lose it, and even mistakenly deleting it may be disastrous. Therefore, we want to introduce a new funtion with which users can actively emphasize importance of a certain file. Operating systems can thus take additional resources to ensure it. 

We want to accomplish it using a smart backup function for EXT2 file systems. Users can actively and consciously use it for significant files, to ensure security of TARGET. 

TARGET is a file in the current working directory. After TARGET has been *sbu*-ed, a new file is created. 

In common cases, the new file will behave like symbolic links. However, when this important file is deleted (or overwritten), either mistakenly or by adversial attackers, will behave like a hard link so that data in the file will be maintained. 

## Input

We hope to implement ls, ln, rm and sbu functions for EXT2 file systems. 

* `ls` *FILE* <br>

List information about the FILE. 

* `ln` *TARGET* *LINK_NAME* <br>

Create a hard link to TARGET with the name LINK_NAME. 

(if possible, we also want to implement symbolic links)

* `rm` *FILE* <br>

Remove (unlink) the FILE using inode. 

* `sbu` *TARGET*

Smart Backup TARGET using inode. 
