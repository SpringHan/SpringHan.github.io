---
title: Arch系下 pnpm 使用时的权限事项
date: 2026-10-04 23:55
tags: [linux, nodejs]
summary: 在 Arch 系下使用 pnpm 时遇到权限的问题
---

最近在使用 dsh 准备安装插件的时候，发现插件的安装刚需`pnpm`，我用 pacman 安装了之后运行安装命令后又发现出现了权限相关的错误。问过 AI 后，发现问题出在 pacman 安装了 pnpm 后，所有用户的全局包存储的文件权限都被 root 用户所持有。

最后的解决方案是使用`chown`命令将权限重新分配给当前用户。
