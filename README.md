# README: Make a Resume Website Using Markdown, Git, and Hugo

*Author: Kweku Assan*  
*Date: 2025-03-06*  

---

## 1. Title

**“Create a Simple Resume Website with Hugo and Git”**

---

## 2. Purpose

This README explains how to turn a basic resume file (written in Markdown) into a live website. We will use:

1. **Markdown** to write the resume.  
2. **Git** to track all changes.  
3. **Hugo** to turn Markdown files into a website.  
4. **GitHub Pages** to host the final site online.

We assume you are like **Marvin**, who has read Andrew Etter’s *Modern Technical Writing* but has very little experience with Git or website tools. We will follow Etter’s ideas about keeping writing simple, using lightweight markup, and publishing quickly.

---

## 3. Audience

- **Who:** Marvin or anyone who can do basic tasks on a computer, like opening a terminal or using a file explorer.  
- **Why:** They want to create a simple website for their resume while using modern documentation practices.  
- **Key Tips from Andrew Etter:**  
  - “Define the Audience” so your writing stays focused.  
  - “Use Lightweight Markup” like Markdown.  
  - “Use Distributed Version Control” like Git.  
  - “Publish Frequently” so changes go live fast.

---

## 4. Prerequisites

1. **Markdown Resume**  
   - You need a file named `resume.md`, created in Markdown.  
   - Keep it brief and well-structured. (Etter says not to write more than necessary.)

2. **Git Installed**  
   - Git is used to track changes in your files.  
   - Download it here: [https://git-scm.com/downloads](https://git-scm.com/downloads)  
   - It works on Windows, Mac, or Linux.

3. **Hugo Installed**  
   - Hugo changes your Markdown into HTML.  
   - Follow instructions here: [https://gohugo.io/documentation/](https://gohugo.io/documentation/)

4. **GitHub Account**  
   - Sign up at [https://github.com/](https://github.com/) if you do not have one.  
   - We will store your files there, and use GitHub Pages to host the site.

5. **Basic Terminal Skills**  
   - You should know how to open your Terminal (or “Command Prompt” on Windows).  
   - You can run commands by typing them in the Terminal and pressing Enter.  
   - If you prefer, copy and paste the commands exactly.

---

## 5. Step-by-Step Instructions

These steps follow Pfeiffer’s guidelines for instructions: keep steps short, use one main action per step, and write clearly. We will also refer to Andrew Etter’s ideas along the way.

### 5.1 Write or Adjust Your Markdown Resume

1. **Open a Text Editor**  
   - Use any editor that supports Markdown (like Visual Studio Code, or a plain text editor).  

2. **Create or Update `resume.md`**  
   - Keep only the information you need, such as education, work experience, and skills.  
   - Example:
     ```markdown
     # John Doe Resume

     **Education**  
     BSc in Computer Science
     ```
   - Etter says “Don’t Write” more than you have to.

### 5.2 Prepare a Local Project Folder

1. **Make a Folder Named `resume-site`**  
   - Store your `resume.md` and this `README.md` inside it.  
   - This follows Etter’s “Don’t Duplicate” rule by having a single source folder.

2. **Open Your Terminal**  
   - Navigate (change directory) so you are *inside* the `resume-site` folder.  
   - For example, on Windows you can type:
     ```bash
     cd C:\path\to\resume-site
     ```
   - On Mac or Linux it might be:
     ```bash
     cd /home/username/resume-site
     ```

### 5.3 Initialize Git and Make Your First Commit

1. **Initialize a Git Repository**  
   - In your Terminal, run:
     ```bash
     git init
     ```
   - This sets up Git in your folder.  
   - Etter’s principle “Use Distributed Version Control” says you should track all changes so others can help if needed.

2. **Add and Commit Your Files**  
   - Type:
     ```bash
     git add .
     git commit -m "Add resume and README"
     ```
   - Git now tracks `resume.md` and `README.md`.  
   - Committing means you saved a “snapshot” of your project.

### 5.4 Install Hugo and Make a Site

1. **Check Hugo Installation**  
   - In Terminal:
     ```bash
     hugo version
     ```
   - If it shows a version number, Hugo is ready.  
   - If not, follow [https://gohugo.io/documentation/](https://gohugo.io/documentation/) to install.

2. **Create a Hugo Site in the Same Folder**  
   - In `resume-site`, run:
     ```bash
     hugo new site . --force
     ```
   - This adds Hugo folders like `content`, `themes`, `layouts`.

3. **Move `resume.md` to the `content` Folder**  
   - Rename your file from `resume.md` to `content/resume.md`.  
   - Hugo looks at `content/` when building pages.

4. **Add a Theme (Optional)**  
   - Themes help you avoid writing HTML yourself.  
   - Example:
     ```bash
     git submodule add https://github.com/theNewLeif/emerald.git themes/emerald
     ```
   - Edit `config.toml`:
     ```toml
     theme = "emerald"
     ```

5. **Commit Changes Again**  
   - Run:
     ```bash
     git add .
     git commit -m "Add Hugo files and theme"
     ```
   - Keeps your Git log organized.

### 5.5 Test Your Site Locally

1. **Run the Hugo Development Server**  
   - In `resume-site`, type:
     ```bash
     hugo server
     ```
   - Hugo shows you a local address like `http://localhost:1313`.

2. **Open That Address in Your Browser**  
   - Check if your resume content appears.  
   - If you need changes, edit `resume.md` then refresh the page.

3. **Commit After Fixing Problems**  
   - Every time you are happy with changes:
     ```bash
     git add .
     git commit -m "Update resume and site"
     ```

### 5.6 Publish on GitHub Pages

1. **Create a GitHub Repository**  
   - Go to GitHub, make a new repo called `resume-site`.  
   - Leave it empty (no auto README) so we can push our existing files.

2. **Link Local Git to GitHub**  
   - In your Terminal, run:
     ```bash
     git remote add origin https://github.com/<YourUsername>/resume-site.git
     git push -u origin main
     ```
   - Replace `<YourUsername>` with your GitHub username.

3. **Generate the Final HTML**  
   - In `resume-site`, run:
     ```bash
     hugo
     ```
   - Hugo places finished pages in `public/`.

4. **Deploy to a Separate Branch**  
   - Go inside `public/`:
     ```bash
     cd public
     git init
     git checkout -b gh-pages
     git add .
     git commit -m "Deploy site"
     git remote add origin https://github.com/<YourUsername>/resume-site.git
     git push -u origin gh-pages
     ```
   - This puts the built files on a branch named `gh-pages`.

5. **Turn on GitHub Pages**  
   - On GitHub, open your repo.  
   - Click “Settings” then “Pages.”  
   - Choose `gh-pages` as the source branch.  
   - Your site link will look like:  
     ```
     https://<YourUsername>.github.io/resume-site/
     ```
   - Wait a minute and your site should go live.

---

## 6. Further Resources

1. **Markdown Guide**  
   [https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/)  
   Helpful if you forget how to do headings, links, lists, etc.

2. **Hugo Documentation**  
   [https://gohugo.io/documentation/](https://gohugo.io/documentation/)  
   Explains how to install Hugo, use themes, and troubleshoot.

3. **Sample Resume Templates**  
   [https://templates.office.com/en-us/resumes-and-cover-letters](https://templates.office.com/en-us/resumes-and-cover-letters)  
   You can borrow a layout idea, then convert it into Markdown.

---

## 7. FAQ

1. **Why use Markdown instead of raw HTML for the resume?**  
   - Andrew Etter recommends “lightweight markup” since it is easy to read and edit. HTML can be complicated if you only want a simple text layout.

2. **I updated `resume.md` but my site is not updated online. Why?**  
   - Make sure you re-run `hugo` to generate new pages.  
   - Then commit and push changes to `main`.  
   - Finally, push the new `public/` folder to `gh-pages`.  
   - If GitHub Pages is set to `gh-pages`, your live site should refresh soon.

---

## 8. Credits

- **Author:**  
  - *Name:* **Kweku Assan**  

- **Peer Reviewers / Classmates:**  
  - *Peers :* Ethan Harper & Kim Yunwhan

- **Theme / Third-Party Assets (if used):**  

- **References:**  
  - Andrew Etter, *Modern Technical Writing*  
  - [GitHub Help Documentation] (https://docs.github.com/en)

---

## 9. Final Thoughts

You just turned a Markdown resume into a small website using Hugo and Git. This matches Andrew Etter’s advice to:

- **Use lightweight markup** (Markdown).  
- **Manage your files in a DVCS** (Git) so changes are easy to track.  
- **Publish frequently** so your resume stays up to date.  

Congratulations on building a modern documentation project! 
