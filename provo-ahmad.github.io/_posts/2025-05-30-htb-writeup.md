---
title: "HackTheBox Writeup: Mischief"
date: 2025-05-30
categories:
  - writeups
tags:
  - htb
  - web
  - reverse shell
---

## Summary

This is a quick walkthrough of **HTB - Mischief**. It was a fun web challenge with some tricky logic bugs.

```bash
nmap -sC -sV -oN scan.txt 10.10.11.124
```

Found port `80`, did Gobuster:

```bash
gobuster dir -u http://10.10.11.124 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

Got reverse shell via PHP upload → privilege escalation via sudo misconfiguration.
