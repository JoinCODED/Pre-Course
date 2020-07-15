### Topics to discuss:

- What Netlify is.
- How to deploy using Netlify.

[Netlify](https://www.netlify.com/)

# What is Netlify?

Netlify is a web developer platform that allows you to easily, quickly, and securely deploy your websiet. It works very well with Git, and using it to deploy a new website takes no time.

# How to deploy a websiet using Netlify

First, you need to push your portfolio website to a GitHub repository. Follow these steps to do that:

1. Go to [GitHub](https://www.github.com/).
2. Create a new repository. Name it "Portfolio", preferably.
3. In your Terminal, `cd` into your `Portfolio` directory, where your portfolio files are.
4. Run the following commands to create a git repository locally:

   ```bash
   $ git init
   $ git add .
   $ git commit -m "First commit"
   ```

5. On GitHub, copy the two terminal commands you see at the bottom of the page, below the bold text that says: "**…or push an existing repository from the command line**"
6. Paste the two commands in the Terminal.

Let's deploy our portfolio website to Netlify! Here are the steps:

1. [Signup on Netlify using your GitHub account](https://app.netlify.com/signup)
2. Click the button that says "New site from Git".
3. For the first step under "Continuous Deployment", choose "GitHub".
4. If it asks, authorize Nelify.
5. On the second step, search for a click on the repo you just made on GitHub.
6. On the third step, keep the default options, scroll down and click "Deploy site".

That's it! Your website is now officially live! You can find the domain name in green in the middle of the screen. You can change it...

1. Click on "`Domain settings`".
2. Click on "`Options`" > "`Edit site name`" to edit the name of the domain name.

There you go! The domain name is of your choosing, and the website is live! Congratulations!

## Task

(Set the time limit.)

Deploy your website on Netlify!
