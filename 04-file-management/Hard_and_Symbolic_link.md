# Hard and Symbolic Links + inode
## Hard Links
Every file on the Linux file system starts with a **single** hard link. This link is between the filename and the actual data stored on the file system.
For eg. If I create a file with the name `file1` and write `foo` in `file1` then the link between `file1` and the data stored in the file is called a hard link. I can verify the number of hard links a file has by typing `ls -l`. You see the numerical 1, it depicts this file has 1 hard link.

<img width="620" height="73" alt="image" src="https://github.com/user-attachments/assets/acedbcd3-9019-4a8a-8905-507843009167" />



We can use the cat command to see the contents of a file. `cat file1` shows me the contents of file1.
The syntax for creating hard links is `ln <original file path> <new file path>`

So let us create a hard link to `file1`: I will type `ln ~/file1 /tmp/file1_hl`. Here I'm creating the hard link to `file1` in the `tmp` directory.

<img width="724" height="121" alt="image" src="https://github.com/user-attachments/assets/a357ba65-a126-47f9-b481-7f0df3611c90" />


If I do `ls -l file1` I see this file now has 2 hard links. The 1st was automatically created when file1 was first created and the 2nd one we just created. Similarly, if I do `ls -l /tmp/file1_hl` I see 2 hard links. 
Here we know `file1` and `file1_hl` are hard-linked, but if you find two files with identical properties but are unsure if they are hard-linked, use the `ls -i` command to view the inode number. 

> Files that are hard-linked together share the same inode number.

<img width="598" height="97" alt="image" src="https://github.com/user-attachments/assets/1e5086a5-c358-40ad-aaef-5e65849a4bec" />


**What is an inode?**
Every file in Linux gets an inode. Inodes in Linux store metadata for every file on your system. Metadata like the location of the file on the disk, permissions, size, owner/group info. and much more. They store all the information except the file name and the actual data.

Hard links essentially point to the same inode number. We can check the inode number using `ls -i.`
`ls -li file1 /tmp/file1_hl` gives me a long listing because I used the `-l` option and also the inode because I used the `-i` option. You see I just **chained 2 short options** together. 
What we see in the output is, we have the same inode no., which implies they have the same data. 

<img width="882" height="74" alt="image" src="https://github.com/user-attachments/assets/78e618bc-817d-4818-9dae-e885b4737e4a" />


Since they point to the same inode, if I change the content of `file1`, then `file1_hl` will also show the changed content. Let's add another line to `file1`: `echo "bar" >> file1`.
I will `cat file1` now and I see `foo bar`. Now let's `cat /tmp/file1_hl` and I see the same content.

<img width="613" height="167" alt="image" src="https://github.com/user-attachments/assets/ef4dd1e1-dad4-4fe9-a53b-cade02e06828" />


`echo` is used to enter text in a file or output text. When used with `>` it overwrites the existing text in the file and with `>>` it appends the supplied text in the file. I will elaborate on these in later lessons. 

I want you to understand that you can create many hard links to a file and they will have the same inode. The inode is only deleted when **all** the hard links are deleted.

> Note: Hard links are only valid within the same File System. Symbolic
> links on the other hand can span file systems as they are simply the
> name of another file.


## Symbolic Links (aka Symlinks)
Symlinks are like shortcuts in Windows OS. If the original file is deleted then the shortcut is of no use. Similarly, if a file to which a symlink points to is deleted then the symlink is of no use. This situation is known as the dangling symlink or a broken symlink. If you recreate the file to which the symlink was pointing to the symlink starts functioning again.

The syntax of creating symlink is `ln -s <original file path> < new file path>`. Syntax is similar to hard link, you just have `-s` extra.
Let's create `file2` and put some content in it. I'll add `foo bar` to it. I will now create a symlink by typing `ln -s ~/file2 /tmp/file2_sl`. I'll now check the inode for `file2` and its soft link.
`ls -li file2 /tmp/file2_sl`. You see the inodes are different, this is the reason the symlink is of no use when the original file is removed, as the symbolic link points to the original file whereas hard links point to the actual data, not the filename.
<img width="1105" height="149" alt="image" src="https://github.com/user-attachments/assets/53e443de-96a0-4438-8df4-a1ccd619a48d" />


The following snip shows a situation when the original file to which the symlink points to is deleted.

<img width="1127" height="122" alt="image" src="https://github.com/user-attachments/assets/eff1b002-51dd-4359-aec5-30e4f479503c" />


`rm` command is used to remove files.
`file` command helps determine the type of a file and its data.


> You would often hear symbolic links referred to as **soft** links. Refrain
> from calling them soft links as the Linux community doesn't like this
> term.

> In summary: A Symbolic is a reference by name to the original file, while a hard link is a dire
