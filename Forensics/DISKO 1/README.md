# Overview
- Tags: `Easy` `Forensics` `picoGym Exclusive`

# Description
Can you find the flag in this disk image?  
Download the disk image [here](https://artifacts.picoctf.net/c/538/disko-1.dd.gz). 

# Hints
Maybe Strings could help? If only there was a way to do that?

# Solution
First let's download the disk file that we need using the `wget` command:

`bsnookie9-picoctf@webshell:~$ wget "https://artifacts.picoctf.net/c/538/disko-1.dd.gz"`

Now let's unzip the .gz file using gzip:

`bsnookie9-picoctf@webshell:~$ gzip -d disko-1.dd.gz`

Once unzipped, we can use two commands the find the flag. First we can use `strings` to print out any strings in the disk image.  
Then we can pipe the result from that to `grep` to search for the beginning part of the flag. These can be done in the same command:

`bsnookie9-picoctf@webshell:~$ strings disko-1.dd | grep "pico"`

```
:/icons/appicon
# $Id: piconv,v 2.8 2016/08/04 03:15:58 dankogai Exp $
piconv -- iconv(1), reinvented in perl
  piconv [-f from_encoding] [-t to_encoding]
  piconv -l
  piconv -r encoding_alias
  piconv -h
B<piconv> is perl version of B<iconv>, a character encoding converter
a technology demonstrator for Perl 5.8.0, but you can use piconv in the
piconv converts the character encoding of either STDIN or files
Therefore, when both -f and -t are omitted, B<piconv> just acts
picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}
```

# Flag
`picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}`
