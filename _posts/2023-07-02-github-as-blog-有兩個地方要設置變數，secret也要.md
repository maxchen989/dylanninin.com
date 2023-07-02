---
layout: post
title: Github as Blog 有兩個地方要設置變數，Secret也要
categories: [Post]
tags : [post]
---

1是Security中要設置
2是env中要設置，這是給workflow用的

![image](https://github.com/MaxwellBest/dylanninin.com/assets/29641586/07509217-437b-459e-bdbb-2f005c4007a0)

https://github.com/dylanninin/dylanninin.com/issues/72

由於work flow中也有用到secret，所以也要配置。
![image](https://github.com/MaxwellBest/dylanninin.com/assets/29641586/0647d459-a903-45b0-8ec7-9c48d7c12587)

需將workflow權限設定為r/w否則會出現：

Run git config --global user.email "xxxx@gmail.com"
[master 3d65297] update post - skip ci
 1 file changed, 5 deletions(-)
remote: Permission to ***.git denied to github-actions[bot].
fatal: unable to access 'https://github.com/***/': The requested URL returned error: 403
Error: Process completed with exit code 128.

![image](https://github.com/MaxwellBest/dylanninin.com/assets/29641586/7dc3f4c5-3370-4926-b787-f5f9c8bf5684)


