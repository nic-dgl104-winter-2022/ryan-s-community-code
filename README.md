# ryan-s-community-code

Community Code Project - DGL 104
Ryan Stich

Solidity: Initially I was going to choose solidity for my community code project, but because this is a brand new language I just couldn’t manage to garner the time to construct anything. Although the language seems interesting and rooted in a fast-paced coding community, for me to get that initial learning under my belt in order to have anything to show for myself would have taken quite a few extra hours. So ultimately I had decided to go with a library for my favorite language. I wrote about how much I had enjoyed my time years ago in the past when I was learning the entry-level beginnings of THREE.JS, and after writing that I decided that this would fit perfectly within my community code project. Since I am very familiar with javascript & even have a tiny bit of surface-level knowledge within the library itself I thought this would give me a slight advantage to hopefully produce a small project at the end and showcase the skills that I have learned. Although the community is growing ultimately my goal would be to eventually get into 3D modeling and create some fun & forward-thinking 3D projects of my own. Although I don’t think there is a ton of demand for front-end three.js developers, sometimes I like to allow myself to get lost in some creative code and just have fun outside of the business and all the work. 

Week 1


COMMUNITY CODE: Identify the community site that you think will be the most valuable for you to regularly engage with throughout the semester. If the site requires a user profile then you should make one, if you haven't already done so. Here are a few things you should do this week:

Week 1


So after looking for a few resources regarding my learning within three.js I have located a course that I bought a long time ago and a discord channel that is very active. 
Course - https://threejs-journey.com/
Discord - https://discord.com/invite/6EHuVam
This course goes incredibly in-depth into not just the surface level elements but also the much more complex areas of three.js development such as lighting, shadows, physics, custom models, imported models, post-processing, etc… The thing that I am most interested in is the imported models and created models in blender. I’ve found it extremely cool that there is almost live game development taking place in your browser with WebGL & Three.js. Now obviously we can’t run AAA series games in the browser but it is always impressive when you see a well-done creative code project. When I run into issues I will be engaging via the discord as there are help sections when it comes to creating code and getting through the more complex parts of the course. Although I won't be enrolling in the entire course as it's over 100 hours of content, I am still hopefully aiming to create something that I can share at the end of this project. 







COMMUNITY CODE: This week should be about writing some simple code that is related to your community. Writing code could encompass a variety of activities, depending on your level of expertise in the language you've chosen to work in. Here is a loose scale that represents possible activities from pure novice to more comfortable:
 
For example, if you are new to the programming language related to your community, then you should work on tutorials that help to get you up to speed.
Or, if you are already comfortable with the programming language related to your community, but you have some learning goals associated with a tool / technology / framework associated with that community and language, then you should start writing code to help you use that tool / technology / framework.
Finally, if you are very comfortable with the programming language related to your community and you want to help by growing the community, then I would expect you to start experimenting with the existing community codebase in order to find potential issues or features to work on.
 
No matter if you choose one of the above suggestions, or go with something completely different, remember that the goal for this week is just about writing some easy code to get you started with the community. Think of it as your very own "hello world" project.

In week 2 I cracked open the course and dove into the surface level tasks that are required in order to actually set up a THREE.JS environment. In this course, the instructor provides a basic webpack environment. In order to run and get access to all the hidden classes that three.js has to offer, we need to run a server. Of course, there are multiple ways of doing this but to avoid extra work I’ll just be following the tutorial assets that include this bundler. 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04 - Webpack</title>
</head>
<body>
    <canvas class="webgl"></canvas>
</body>
</html>

So when it comes to the first creation of three.js, we need a canvas that we can render our code. If you do not provide one yourself in canvas and modify it with CSS I have found that three.js just hijacks the code and creates a canvas itself that most often times can feel uncontrollable. From here in a javascript file we need to setup our actual three.js code. 

To do that we will a scene, an object that we wish to render, a camera & a renderer. The code provided in the tutorial on the surface looks very tame but gets incredibly more complex as you begin to create different shapes and meshes within your canvas.

// Scene
const scene = new THREE.Scene()
 
// Object
const geometry = new THREE.BoxGeometry(1, 1, 1)
const material = new THREE.MeshBasicMaterial({ color: 0xff0000 })
const mesh = new THREE.Mesh(geometry, material)
scene.add(mesh)
 
// Sizes
const sizes = {
    width: 800,
    height: 600
}
 
// Camera
const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height)
camera.position.z = 3
scene.add(camera)
 
// Renderer
const renderer = new THREE.WebGLRenderer({
    canvas: document.querySelector('canvas.webgl')
})
renderer.setSize(sizes.width, sizes.height)
renderer.render(scene, camera)
Within the renderer, you can see that we are rendering to the canvas that we had created in the html file.

Week 3

COMMUNITY CODE: At this point we're about four weeks into the community code project, including reading week. There are two key things you should have in hand right now:
 
An idea how you want to contribute to your community: This idea doesn't have to be complete or final - there is time to change your idea as you progress with your work - but you should be able to articulate something that describes a potential contribution (see below for contribution ideas).

Week 3

As a beginner in working with webgl and THREE.JS i thought that a meaningful contribution to the community would be to write a welcoming post. After learning the basics of cameras, textures, materials and entry level things such as that it can be pretty overwhelming. I think making an article explaining what WebGL actually is and why people use Three.js would be a helpful and meaningful article to share with the community. When I was first learning I only really understood the visual aspects but I didn't really understand proper use applications or what the purpose of learning the language was, or even really what it entailed. To jump in and start creating some minimal code is pretty easy given that you have some sort of tutorial to follow or document to build from. However i would like to create sort of like a “is three.js worth learning” type of guide, that overlays how much time you would likely need to learn and what it actually entails. As I am still a student of the library and far from an expert, I don't think that i’ll be able to write a guide on how physics works with your own custom models built in blender, but i can write something that would have appealed to me multiple weeks ago getting started. In terms of my own contribution to learning and advancing as a developer i’d like to build out a small little project alongside my guide. I’m not entirely sure what that project will be, i think i would either like to create something with some particles or maybe grab a free model and import it into a scene because i’ve always found to be so interesting. So at this point my community contribution is set in stone but my coding contribution to my own learning is up in the air!



Community Code Contribution Document

Should you learn webgl & three.js as a developer?

Three.js is a 3D javascript library that allows developers to create 3D experiences that live on the web, & inside your code. But first before we can dive into the intricacies of three.js We have to understand what WEBGL is. WEBGL is actually what allows the magic to take place behind all that code you’ve written. WEBGL allows for the 3D to take place inside of your web browser, rendered to a canvas. You may notice that some three.js website run really well on your computer, but you might also notice that some run horribly and cause a bad user experience. But why is this? For example lets take a look at a relatively intensive website. 
https://lusion.co/ This website is stunning upon first view, but what if you’re running an outdated machine? Well this is where you can run into problems. The rate at which your gpu can process the code that is written can effect the overall user experience. That is why some developers tend to be against heavily animated websites and creative coding when it comes to websites that ultimately have a goal that is required to be met by the end user. Luckily for us WEBGL is incredibly fast and the rate at which i can actually render triangles to your stunning. However WEBGL is incredibly difficult to write code for and is something that is rarely done anymore on the web. And that is where THREE.JS comes into play. You can think of WEBGL as a sort of base layer that sits and reads our code before drawing, and you can imagine that THREE.JS is simply a second layer that we can communicate with, and pass our messages onto WEBGL to be drawn. So whether we want to draw a face, or a circle, or a video game character, THREE.JS can relay that information on our behalf to the javascript api. And while some new developers may find THREE.JS confusing, it is much better than interacting with WEBGL itself to get your dirty work done. Three js gives us the developers that layer of abstraction to bring our ideas to life. But, does that mean its worth it to sink hours upon hours into learning to liven up your front ends? Well that is simply something that is up to you as the developer to decide. Many developers, myself included can sometimes get lost in the work and business mindset that code has to offer. Spending time ironing out the perfect simplistic user experience for our end users to fall in love with. But in that same breathe coding can sometimes feel like a lost passion when it becomes all work and no play. In my opinion THREE.JS bridges the gap between the two. Although there is a very easy way to go overboard with animations and things of that nature, there is also a way that you can use them elegantly to create environmentally rich, unique experiences for your users. So ultimately the decision is yours, would THREE give you an advantage over someone in an employment role? Potentially. 

