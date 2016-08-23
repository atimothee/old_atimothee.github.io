---
layout: post
title: "How to use Facebook Account Kit to authenticate Firebase app users on Android"
date: 2016-08-22 17:01:26 +0300
comments: true
published: false
categories: 
---

A few months ago Facebook released [Account Kit](https://developers.facebook.com/docs/accountkit/overview) which "helps people quickly and easily register and log into your app using their phone number or email address as a passwordless credential".

Account Kit is really really helpful for a couple of reasons; users don't need to remember a password for your app, it supports SMS-based authentication for hundreds of countries, and it's really easy to setup.

Know something else with lots of features, and requires minimal setup? Firebase.
For the uninitiated, [Firebase](https://firebase.google.com/docs/database/) provides a realtime, NoSQL cloud database for apps, and remains available, even when your app goes offline, with minimal setup effort.

Firebase, currently does not provide a direct way to authenticate users with account kit, but this can be achieved used Firebase Custom Authentication.

Firebase Custom authentication allow users to authenticate against an external or legacy authentication mechanism. We will treat Facebook Account Kit as a legacy authentication mechanism.

This post is not a tutorial on how to use Firebase, neither is it one about how to use Account Kit on Android. Basic knowledge of how Firebase and Account Kit work is assumed.


One of the awesomest features of Firebase is it provides FirebaseUI, a drop-in auth solution that handles the UI flows for signing in users with email addresses and passwords, Google Sign-In, and Facebook Login.

is Firebase Authentication.

However, Firebase supports Custom auth system integration. To use Account Kit to authenticate Firebase users, we shall use custom auth.

To use custom, we need to setup an authentication server, which generates custom tokens, which can then be used sign into the Firebase Authentication service in the android app.

This tutorials assumes you've already configured your android projec to use firebase authentication.

{% gist 1027674 %}

T

Firebase has a Server SDK for Java and NodeJS. We will use Java for this tutorial, and we'll use Google Cloud endpoints , (because all the code lives inside Android Studio)