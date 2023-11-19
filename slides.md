---
theme: seriph
colorSchema: light
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Introduction to PocketBase
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
title: Introduction to PocketBase
mdc: true
---

# Introduction to PocketBase

## An open source, portable Firebase alternative

<div class="abs-bl m-6 flex flex-col text-left">
  <p class="!m-0 !mb-2 text-3xl">Ned Palacios</p>
  <p class="!m-0 text-md font-italic">for Davao Interschool Computer Enthusiasts</p>
  <p>ned@nedpals.xyz</p>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
Hey everyone, maayong gabii! Magandang gabi and madayaw davao! To everyone who's joining tonight, welcome to the DEVCON Davao online geekup hosted by us Davao Interschool Computer Enthusiasts.

Tonight, I will be introducing to you to PocketBase which is an open-source alternative to Firebase and hopefully your next backend for your next project.
-->

---
transition: fade-out
title: Who am I?
---

<div class="flex flex-col text-left mt-16 items-start">
  <p class="font-italic">Who am I?</p>
  <h1>Ned Palacios</h1>

  <v-clicks>
    <ul>
      <li>4th year CS student</li>
      <li>Student developer (Web / DX)</li>
      <li>Former Lead, GDSC UIC ('22-'23)</li>
      <li>Founder / Student Relations Lead, DICE</li>
      <li>Member, DEVCON Davao</li>
    </ul>
  </v-clicks>
</div>

<div class="absolute top-0 inset-x-0 flex justify-end">
  <img src="me.png" style="filter: grayscale(1) brightness(1.3)" class="w-[68%]" />
</div>

<!--
Before we start, I would like to introduce myself. So my name is Ned Palacios.
- Currently I'm a (hopefully graduating) 4th year computer science student at the University of the Immaculate Conception.
- So I'm also a student developer currently focusing on building stuff on the web and creating tools for enhancing developer experiences.
- I am the last year's lead of Google Developer Student Clubs UIC
- and this year, along with 6 other student leaders, we founded DICE of which I am the org's student relations lead.
- Of course, I am a proud member and volunteer of DEVCON Davao :>> (Technically, this is my first ever DEVCON talk after how many lightning talk sessions na nangyari xD)
-->

---
layout: center
title: Links
---

<p class="!text-6xl">Slides: <a href="https://github.com/nedpals/pocketbase-devcon-slides">https://github.com/nedpals/pocketbase-devcon-slides</a></p>
<p class="!text-6xl">Project Repo: <a href="https://github.com/nedpals/pocketwitter">https://github.com/nedpals/pocketwitter</a></p>

---
transition: fade-out
preload: false
title: Firebase
---

<div class="flex flex-col items-center justify-center h-full">
  <img src="Firebase_Logo.svg" class="h-auto w-1/2 mb-8" />
  <h2>Backend-as-a-service</h2>
</div>

<!--
For our first question: how many of you know about Firebase? (**pause for a moment**) How many of you here use Firebase? (**pause for a moment**)

But for those who don't really know Firebase. Firebase is what we call a "backend-as-a-service": basically all the common things that you gonna build as a developer that may seem hard or boring to you is already built by the service. For example: database, authentication, file storage, and realtime data. It's up to you already which of these you will use and you can just easily add or remove them anytime.
-->

---
layout: center
---
# Firebase Benefits

<v-clicks>

- Saves time
- Little to no friction
- Focus on the idea
</v-clicks>

<!-- 
The benefits for this as a developer are simple. First, it saves time especially to some of us who are not that good yet in programming a backend from scratch. Second, there's little to no friction at all. You don't need to setup a server, all you need is to integrate it via their provided SDK to your favorite framework. With that said, you just basically focus on your idea. Whether if it's just a side project, an MVP, or just want to try something new - the backend should not hold back the product you want to build.
-->
---
layout: center
---
# Firebase Roadblocks

<v-clicks>

- Expensive to scale
- Hard to migrate
- Requires online connectivity
</v-clicks>

<!--
It sounds to good to be true. However, when you see the potential of your project and want to be fully serious about you'll gonna be hitting the roadblocks in a short amount of time. And that cost of hitting those roadblocks in Firebase won't be cheap. At the same time, if you want to migrate to something cheap, it also won't be very easy  it does not use any open formats and standards. Lugi ka.
as

And that minimal friction? There's an if to that. If your place does not have a working internet connection, it will be the end of the world for you. Of course there are solutions to this but then they are from third parties and not from Google themselves which won't be reliable.
-->
---
layout: default
---

# Open Source Firebase Alternatives

||Supabase|Appwrite|
|-|-|-|
| |<img src="https://seeklogo.com/images/S/supabase-logo-DCC676FFE2-seeklogo.com.png" class="w-1/5" />|<img src="https://miro.medium.com/v2/resize:fit:384/1*GftqhTAzDylbY-CISlvkvw.png" class="w-1/5" />|
|**GitHub stars**|59.4k stars|37.9k stars|
|**Database**|PostgreSQL|MariaDB|
|**Features**|Auth, realtime, storage, functions|Auth, realtime, storage, functions|
|**Cloud offerings**|Yes|Yes|
|**Official SDKs**|Yes|Yes|

<!-- 
There are now projects that tackle these problems: Supabase and Appwrite. Two of the most popular Firebase alternatives by the time I made this presentation. They have more or less the same set of features as Firebase, they have SDKs with similar experience as Firebase, but most importantly, they are open source which means that aside from running it in the cloud you can run the platform itself in offline or in your cloud provider of choice and they also use tried and tested components such as SQL databases. 

"Ned, I think we already have the solutions to our problems right?" Well, not quite. You see, while I did mention earlier that you can run them by yourself (because it's open source), setting up takes a lot of time and compute resources (aka your computer's CPU, RAM, and storage) which defeats the purpose. It assumes that you know all the super technical stuff (e.g. Docker) upon setup which makes it not very attractive for just a simple project. This is where PocketBase comes in.
-->

---
layout: section
title: Introducing Pocketbase
---

# Introducing Pocketbase

<!-- 
PocketBase is an open-source backend-as-a-service (BaaS) that was launched last July 2022 and it has everything you need (authentication, database, realtime, and storage).
-->
---
layout: center
title: Obligatory XKCD comic
---

![Standards](https://imgs.xkcd.com/comics/standards.png)
[https://xkcd.com/927/](https://xkcd.com/927/)

<!--
You might be thinking, solving the problems of Firebase alternatives with another Firebase alternative? How do you say so?
-->

---
layout: center
---
# Why Pocketbase?

<v-clicks :depth="2">

- Authentication, database, realtime, and storage all in **one executable file**.
  - Self-hostable and **can run offline**
  - Deploy the executable in your favorite VPS or deploy via Docker
- Fast, performant, and reliable because it is **written in Go**
- Under the hood it uses the **SQLite** database to store data
</v-clicks>

<!-- 

There are multiple reasons why you should use Pocketbase over Firebase and other alternatives.

[1] Instead of having separate for each feature which is the case for others, which is the reason for using Docker in the first place, everything is integrated into a single executable. This means you don't need to manage any dependencies. Simply run the executable on your computer, and you're ready to go.

That means you can host it by yourself easily and can run without an internet connection. Speaking of hosting, you can get up and running by just putting the file into your server, tweak something in your server, and done. If you want to automate it, you can still deploy it via Docker. 

[2] Pocketbase is written in Go. Go is a general-purpose programming language created by Google created to build Google-scale applications so this means that is can cater hundreds and thousands of requests without breaking a sweat.

[3] Lastly, the reason why PB makes this possible is because it does not use any typical traditional database similar to what Supabase and AppWrite. Instead, it uses SQLite which is a database that we often see when we develop mobile applications. Make no mistake, SQLite is really as it eliminates any additional setup.
-->
---
transition: slide-up
layout: center
level: 2
---

# Demo / Setup

We will be building a simple Twitter clone:
1. Login / register
2. List / create / delete posts
3. Make / list comments
4. Favorite tweet

Repo: https://github.com/nedpals/pocketwitter

<!--
To demonstrate how simple it is to get up and running. We will have our demo!

But before that, the application we will be building is a simple Twitter clone. We will have the following functionalities. *refer to the slide*

**proceed to presenting the screen**

1. Go to pocketbase.io, and upon arriving you will see the screenshot of our dashboard. Basically, the dashboard is where we will go after we download it. 
2. To download, scroll and click the "Read the Documentation" button in which it will redirect you to the setup guide. Click the download appropriate to your operating system and wait for a minute. Once you are done, extract the zip file to the location where you would like it the best.
3. Go to the pocketbase folder you have just extracted and open your terminal from there.
  - For Linux, you can just right click the file manager and click "Open in Terminal"
  - For Mac, you can just drop the folder to your terminal
  - For Windows, you need to press shift + right click on an empty area in your file explorer and select "Open in Windows Terminal" or similar ("Open in command prompt" or "Open in Powershell" will do).
4. Once you are now in the terminal, type in `./pocketbase serve` (or `.\pocketbase.exe serve` for Windows) and once you see that there's a URL to that (zoom in), take note of that URL and open that in your browser.
5. If you have opened it in the browser, you may see a white screen. This is actually okay because what you are seeing is part of the REST API of your Pocketbase instance. To go to our dashboard, we just simply add slash (if not present) followed by underscore (_) so it should be like this (http://localhost:8090/_) and hit enter. This will proceed to the setup which should be.
6. Upon arriving at the setup, it should look like this (**present it into the screen**). Fill up the details as you want. If you are unsure of what you are doing, you can just have example@example.com as the email and 1234567890 as the password since it requires you to have your password to be atleast 10 characters.
7. Once you are done, then that's it! 
**Go back to slides**
-->

---
layout: center
---

# Basics

<v-clicks :depth="3">

- **Record** - individual entries in a collection
  - Firebase: **document**
  - Database: **row**
- **Collection** - organized groups of related records
  - Firebase: **collection**
  - Database: **table**
  - Has a schema = **structured**
    - **column** = **field**
  - Three types:
    - **Base** Collection
    - **View** Collection
    - **Auth** Collection
</v-clicks>

<!-- 
Now you have seen how simple and easy it is to get up and running which is really important since this is what we are aiming for. Let's talk about the basics.

One think I have not mentioned before is that there are alternatives who would like to reinvent the wheel by explaining concepts in one to two paragraphs as if the relational databases don't exist. Here in PocketBase, the concept just follows like a relational database albeit they are just renamed to make it more easier for the users to grasp. So in Pocketbase:

- Each individual entries in a collection is called a **record**
  - In Firebase, you may call it a **document**
  - And in traditional database, this is called a **row**
- In reverse, an organized groups of related records is called a **collection**
  - This is still called **collection** in Firebase
  - And in traditional database, this is called a **table**
  - Unlike Firebase, the records are structured through a defined schema. So you'll have to define the structure of the data you want to put inside a record.
    - Each property defined in the schema is called a **field** which is the equivalent of **column**
  - There are three types of collections:
    1. Base collection - the default collection type for application data
    2. View collection - a special type of collection that derives data from other collections. Perfect if you want a pre-filtered list and don't want to create that logic inside of your application code
    3. Auth collection - which is meant for managing user accounts and authentication (Unlike others, the best part of this is that it's not treated as a separate database and you can just make interact it with other collections)

And there you have it!
-->

---
layout: section
---

# Basics Demo

__**Objective:**__ Create collection for **users**, **posts**, and **comments**

<!--
*go back to screen*

Let's go back to our dashboard. On your left, there is a list of collections and on your right is the records list. What's so nice about this is that what you see is what you get. (You have an add button on the top, you get a list of records of that collection and you can edit it by clicking.) 

Our next task is to create a couple of collections: namely users, posts, and comments. Pocketbase already provided us a built-in users collection but just to show you what I've said earlier about auth collections, we will remove this one and re-create it again by clicking the "new collection" button. Type in users (this is in lowercase) and then we select it as an auth collection. In Pocketbase, you get to pick if you want to use e-mail, username, or OAuth login or what we call "Login with Facebook", "Login with X", and etc. Aside from that, we get to decide what would be added in the users so for now let's just add a name field for now. Click "new field" and you will be presented by different field types that you can explore later but for now we will just select "text", type in name, and hit save.

Next is we create a posts collection. Again we click "new collection", let's type "posts", and leave the dropdown as-is since we want it as a base. Let's have a content field for now. We have two options here: we can have it as a rich text if we want formatting or just text if you don't want any formatting. Let's choose text for now and click save.

Now let's make the comments collection. Same thing, we'll have the content field for now same as the post content - use the text field and save.

We now have the necessary collections for our app, let us try to see the contents of our posts collection in the browser. So the good thing about Pocketbase is that it has API documentation built-in which you can see on the upper right side of your screen. Open that one and now we have sample codes for our CRUD either in Javascript and or in Flutter but for now our focus is **scroll down** is to display the JSON you're seeing here in the browser so we copy the URL and paste it into our browser.

Ooh we have a cryptic error here. That means to say that we don't have rights to access the collection. Our solution to this will be discussed that in the next slide.
-->

---
layout: center
---

# API Rules

<v-clicks>

- Flexible and powerful way to control access to your application data
- Similar to Firebase's **Firestore Security Rules**
- By default, the collection can only be accessed by admins *(a.k.a. you)*

</v-clicks>

<!-- 

There are some instances that our collection must be accessed only by us internally or for those who are logged in. Normally us who don't have sufficient experience yet, we typically add that check inside the application code which is a BIG BIG RED FLAG! And people with enough curiosity can still access your API by just copy pasting the API URL (that is, if they figure it out). 

[1] This is where API rules comes in which is a flexible and powerful way to control data of your application. 

[2] If you use Firebase especially those who use Firestore, this is the equivalent of security rules which for me is still difficult to wrap my head over.

[3] Earlier, we saw the error accessing our posts collection. Unlike others, Pocketbase hides the collection to the public by default and you should enable them if you want to let your users read or do whatever they want. (Might be tedious but this is actually a good thing since it trains ourselves to be aware which collections are to be exposed instead of the other way around.)

**go back to screen**

Back to our dashboard and we go to our posts collection. On your left, you will see a gear icon. Click that one and the collection editor will show up. Below the collection name, we have two tabs: first tab when you want to modify the structure of your collection and one for the API rules of your collection. Click the second tab and you will be presented by a list of textboxes with each corresponding action. Each action can have it's own API rule so let's say you just want to list them but not to update you can just enable the list action by clicking the green padlock icon.

There is a syntax when you want to construct an API rules but I'll just give you an example. Let's say I want the creation of posts to be limited to those who logged in and at the same time the ID of the user must be the same as the post user ID. We can just add that by clicking the padlock, and type in `@request.auth.id != "" && @request.data.user = 
@request.auth.id` which will do the trick.

We save this one and again reload the page and it should now display an empty list. Problem solved. Now we can integrate this one into our application.

**go back to presentation**
-->
---
layout: center
---
# Integrate PB to app

<v-clicks :depth="2">

- Provides official SDKs for **Javascript** and **Dart/Flutter**
  - **Javascript**: `npm install pocketbase`
  - **Dart/Flutter**: `flutter pub add pocketbase`
- No SDK for **insert language**? Just use a **REST API**!
- API documentation readily available
- Querying options
  - `filter` - Filters/selects data based on the given query.
  - `fields` - Specify which fields will be returned.
  - `sort` - Sort the data by field, `+` means `asc`, and `-` means `desc`
</v-clicks>

<!-- 

In order to integrate Pocketbase into our Twitter clone. PB provides software development kits or SDKs both for Javascript and Dart/Flutter, for Javascript you just simply type the following NPM command and the same thing in Dart/Flutter.

If you are integrating PB into platforms that don't have official SDK such as .NET, Java, or Swift, then you can use their REST API which we have demonstrated a while ago. 

To use them, you may just refer to their API documentation which you can see in the upper right side in each collection in your dashboard.

**go back to screen**

ADLIB

In our example, we have the Pocketbase SDK in our Twitter project already installed to save time. I have also commented there some code which you can just uncomment it by using the shortcut `control + /` or `command + /` if you are in Mac. Don't worry, I will explain them one by one so you can get along.

To recall, we have to...
- Make our login/register functionality working
- Create and list our posts
- Create and list the post comments

1. If you have already clone our repo, make sure to `npm install` first.
2. Go to `client.js` and uncomment our `pb` constant. Th

**go back to presentation**

-->
---
layout: center
---
# Relations

<v-clicks :depth="2">

- Establish connections between different collections
- `relation` field
- You can existing database relationship structures
  - One-to-one
  - One-to-many
  - Many-to-one
    - Traditional method (dedicated collection)
    - Store multiple IDs in a record
- Load relationships via `expand`
  - Normal expand: `expand=user`,
  - Back-relation expand: `expand=comments(post).user`
</v-clicks>

<!-- 

Because Pocketbase runs on a relational database, it also supports relationships. You can have a collection reference another collection by simply adding a `relation` field which we will gonna be doing in a minute. 

It supports one-to-one, one-to-many, and many-to-many relationships (of which you can do it in two ways: a traditional dedicated collection or make the relation field able to store multiple IDs instead of one)

*go back to screen*

Let's go back to our dashboard. In order for our us to know  who created the post and which post the comment is directed to, we need to add a user relation to our post and a post relation (and another user relation) to our comments.

1. Go first to our posts collection, and click the gear icon. In our fields editor we just click the "add field" button, type in "user" (remember that it should be a singular word since we are only referencing a user), and select "relation". There will be a dropdown which collection we will connect into which is the "users" collection. Make it required and click "save".

Traditionally we will use user_id or similar to it when storing relationships in our database. The reason why we omit the id because this field name will be used later when we want to access when we to load the contents of the relation which we will dive deeper into that.

2. Next we modify our comments collection by going to our comments, click the gear icon button, and add a "post" relation by adding a relation field pointing to posts and the same thing to the "user" relation both of which should be required. After that, click "save".
 -->
---
layout: center
---
# Realtime
- It lets you subscribe to real-time changes in your specific collection.
- You can be notified when a record has been added, updated, or deleted.
- Similar to Firebase's **realtime database**
- Via Pocketbase SDK: `pb.collection(...).subscribe(topic, callback)`

<!-- 

Realtime is a feature that lets you subscribe to changes in your specific collection in realtime. It lets you notify immediately whether a record in a collection has been added, updated, or deleted without calling the API every time. 

This is also similar to Firebase's realtime database but instead of having a separate database for realtime, it just listens to the same database which is pretty cool.

To use this, we just simply call the subscribe method to our chosen collection and specify whether we listen to the entire collection or just a specific record followed by a callback function that we can use to receive any updates from the server.

**go back to screen**

Let's uncomment the following
 -->


---
layout: center
---
# Notable Mentions

<v-clicks :depth="2">

- Storage
  - Via `file` field
  - Supports image resizing
  - Store it in your server or in S3-compatible storage

- Functions
  - Make Pocketbase as a Go web framework
  - Add custom code via Javascript

- Logging / Telemetry
  - Built-in API telemetry support
  - Can detect HTTP 4xx and 5xx errors

- Production
  - Deploy the executable in VPS or in Docker
   
</v-clicks>
---
layout: center
---

# How does it perform?

<v-clicks :depth="2">

- 10,000+ concurrent users (2 vCPU/4GB RAM/80GB Storage $24 on DigitalOcean)
  - Compared to $100 Firebase "on-demand" bill
  <!-- To be fair, there might be factors for the price but you can still do more compared to this -->
- A basic 512MB server can also perform well
  - `<200MB` RAM usage (based on testing w/ custom code via JS)
- Use replication tools like Litestream for reliability on simultaneous loads
</v-clicks>

---
layout: section
---

# Projects using PB

---
layout: two-cols
---

# Valentine Wall
Freedom wall project of GDSC UIC
every February 14

Repo: [https://github.com/gdsc-uic/valentine-wall](https://github.com/gdsc-uic/valentine-wall)

- Previously Go + PostgreSQL
- Migrated to PocketBase as a framework
  - Maintenance became easier + GUI admin

::right::

Image goes here

---
layout: two-cols
---

# DevFest Registration System
Handles registration, e-mail sending,
and screening. For GDG DevFest Davao 2023

Repo: Coming soon

- PocketBase + Custom code via JS
- Completed in 3 weeks
- Runs smoothly on a free 512mb server
- Utilized e-mail sending function
- Storage for receipts

::right::

Image goes here

---
layout: two-cols-header
---

# Backend for toy project

::left::

<Tweet id="1612631668673904643" :width="700" />

::right::

<iframe src="https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2F100000559682978%2Fvideos%2F693424322331309%2F&width=500&show_text=false&appId=1092368998023400&height=281" width="500" height="281" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowfullscreen="true" allow="autoplay; clipboard-write; encrypted-media; picture-in-picture; web-share" allowFullScreen="true"></iframe>

---
layout: center
---

# Takeaways

<v-clicks>

- With Pocketbase, it is possible for you to setup your backend for your project in minutes
- Enjoy cost-effective backend solutions with PocketBase, offering savings compared to other services.
- Provides you flexibility in managing data access with flexible API rules and etc.
</v-clicks>
---
layout: center
---

# Thank you for listening!

- Follow me on Twitter: @npned
- Let's connect on LinkedIn: https://linkedin.com/in/nedp
- Follow me on GitHub: @nedpals
- Follow me on IG: @nedcodes

---
layout: section
---

# Q&A