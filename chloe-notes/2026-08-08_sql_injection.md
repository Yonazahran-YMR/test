# SQL Injection

Alright, time to lock in and get SQL injection straight in my head before the exam. Ngl, this confused me at first because I kept picturing hackers in hoodies typing green code on a black screen, but it’s actually way dumber—it’s basically just websites blindly trusting user input. 

Here’s my breakdown of how it works and how to stop it.

## What is SQL injection anyway?

Basically, it’s when a bad actor types SQL code into a normal input box on a website (like a login screen or a search bar) and tricks the database into running it. 

This clicked for me because of that one webcomic where the kid's name is `Robert'); DROP TABLE Students;--` and it wrecks the school's database. The app wasn't expecting code, just a normal name, but it just slammed whatever was typed right into the query. Oops.

## How it actually happens (the mechanics)

Normally, backend code looks something like this when trying to log someone in:

`SELECT * FROM users WHERE username = 'USER_INPUT' AND password = 'PASSWORD_INPUT';`

If the site isn't sanitizing stuff, what happens if someone types `admin' --` into the username box? 

* The single quote closes out the username string early.
* The `--` tells SQL to treat everything *after* it as a comment and just ignore it.
* Suddenly, the password check vanishes into thin air, and boom—you're logged in as admin without a password. Wild.

## Types of SQLi (keep it simple)

* **In-band SQLi:** The attacker gets the data right back on the same screen. Classic. 
* **Inferior / Blind SQLi:** The page doesn't spit out the data directly, so the attacker has to ask true/false questions to the database (like "is the first letter of the password 'a'?") and wait to see if the page loads normally or throws an error. Painstaking, but it works.
* **Out-of-band SQLi:** The attacker forces the database to send data somewhere else (like an external server they control) because they can't see it on the main page.

## How to not get hacked (The Fixes)

Don't overcomplicate this, there are really just a few main ways to defend against it:

* **Parameterized Queries (Prepared Statements):** This is the gold standard. It basically forces the database to treat user input *strictly* as data, never as executable code. Even if someone types `DROP TABLE`, the database just searches for a user named literally `Robert'); DROP TABLE...`. Problem solved.
* **Stored Procedures:** Similar vibe, keeps the SQL logic on the database side.
* **Input Validation / Sanitization:** Whitelist what's allowed. If a field asks for an age, don't let people type letters or weird symbols into it. 
* **Least Privilege:** Don't connect the web app to the database as the `root` or `admin` user. If the app only needs to read user profiles, give it read-only access. That way, even if someone *does* pull off an injection, they can't delete the whole table.

Okay, that actually makes sense now. Time for a coffee break.