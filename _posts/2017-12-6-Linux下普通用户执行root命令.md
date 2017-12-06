---
layout: post
title: Linux下普通用户用管理员权限执行命令
---

在Linux系统使用普通用户运行的程序，有时候需要用系统管理员权限执行一些命令，由于程序运行的时候，

不方便手工输入密码。可以使用subprocess.Popen实现程序自动填充密码方式。'iwlist eth0  scanning'为需要使用管理员权限执行的命令。

  cmd_list = ['sudo','-S', 'iwlist', 'eth0  scanning']

  password = b'your_password\n'

  echo = subprocess.Popen(['echo',password],

                          stdout=subprocess.PIPE,

                          )

  p = subprocess.Popen(cmd_list,

                         stdin=echo.stdout,

                         stdout=subprocess.PIPE,

                         )
  str1 = p.stdout.read()  ## str1为输出结果



