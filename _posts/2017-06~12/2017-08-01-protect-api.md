---
layout: post
title:  "保护接口的几点想法"
date:   2017-08-01
tags: [security]
---

基于接口行为判断IP是否为黑IP，以此来限制需要保护的接口。比如，发送短信接口，正常的接口行为是，调用广场接口，个人信息接口或商品详情接口，才可能调发送短信。如果不是，列入黑名单。

基于浏览器的接口调用，保证接口通过浏览器调用，nodejs设置根据ua，ip或其他信息，按规则给浏览器设置httponly的签名值，如果无签名值（直接调接口的）或签名值错误，列入黑名单