# Workshop Exercise - Check the Prerequisites


## Table of Contents

* [Objective](#objective)
* [Guide](#guide)
* [Your Lab Environment](#your-lab-environment)
* [Step 1 - Access the Environment](#step-1---access-the-environment)
* [Step 2 - Working the Labs](#step-2---working-the-labs)
* [Step 3 - Challenge Labs](#step-3---challenge-labs)

## Objective

* Understand the lab topology and how to access the environment.
* Understand how to work the workshop exercises
* Understand challenge labs

## Guide

### Your Lab Environment

In this lab you work in a pre-configured lab environment. You will have access to the following hosts:

| Role                 | Inventory name |
| ---------------------| ---------------|
| Ansible Control Host | control        |
| Managed Host 1       | node1          |
| Managed Host 2       | node2          |
| Managed Host 3       | node3          |

### Step 1 - Access the Environment

Login to your host host via SSH:

[Lab IP info](../lab_info/README.md)

> **Warning**
>
> Inlocuieste **172.30.170.X** cu **IP-ul** din tabelul Lab IP info corespunzator numelui tau.

```bash
ssh root@172.30.170.X
```

> **Tip**
>
> Password: 1qaz@WSX

Start the environment:

```bash
[root@localhost rhce8env]# vagrant up
```

> **Warning**
> 
>Wait for vagrant to finish bringing up the environment.

Login to your control host via SSH:

```bash
[root@localhost rhce8env]# ssh user@control
```

Most prerequisite tasks have already been done for you:

* Ansible software is installed
* SSH connection and keys are configured
* `sudo` has been configured on the managed hosts to run commands that require root privileges.

Check Ansible has been installed correctly

```bash
[user@control ~]# ansible --version
ansible 2.8.5
[...]
```

> **Note**
>
> Ansible is keeping configuration management simple. Ansible requires no database or running daemons and can run easily on a laptop. On the managed hosts it needs no running agent.


> **Note**
>
> In all subsequent exercises you should work as the student\<X\> user on the control node if not explicitly told differently.

### Step 2 - Working the Labs

You might have guessed by now this lab is pretty commandline-centric…​ :-)

* Don’t type everything manually, use copy & paste from the browser when appropriate. But stop to think and understand.

* All labs were prepared using **Vim**, but we understand not everybody loves it. Feel free to use alternative editors. In the lab environment we provide **Midnight Commander** (just run **mc**, function keys can be reached via Esc-\<n\> or simply clicked with the mouse) or **Nano** (run **nano**). Here is a short [editor intro](../0.0-support-docs/editor_intro.md).

> **Tip**
>
> In the lab guide commands you are supposed to run are shown with or without the expected output, whatever makes more sense in the context.

### Step 3 - Challenge Labs

You will soon discover that many chapters in this lab guide come with a "Challenge Lab" section. These labs are meant to give you a small task to solve using what you have learned so far. The solution of the task is shown underneath a warning sign.

---
**Navigation**
<br>
[Next Exercise](../1.2-adhoc)
<br><br>
[Click here to return to the Ansible for Red Hat Enterprise Linux Workshop](../README.md)
