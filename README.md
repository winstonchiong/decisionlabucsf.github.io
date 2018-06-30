# Decision Lab website

A quick way for everyone to learn how to use GitHub and Markdown. (Site design based on [al-folio](https://github.com/alshedivat/al-folio).)

## The super-basics
Hopefully, everyone in the lab will be able to:
- Update their own "team" profile
- Update the list of publications
- Add news posts

To do this, you'll first need to understand a little about: 
1. **GitHub**. For our purposes, you can think of GitHub as being like supercharged Google Docs for code. Multiple people can work on the same code, it keeps track of who made what changes and when, it's easy to reverse changes that have been made, and different versions can be developed at the same time. One nice feature for our site: instead of directly editing in HTML (which is not a language really meant for humans to understand), you'll be giving GitHub information in two human-readable formats, which a GitHub tool called Jekyll will use to generate the HTML. 
2. **Markdown**. This README.md file is written in Markdown. Markdown allows for simple formatting like **bold** (double asterisks like this: `**bold**`), *italics* (single asterisks like this: `*italics*`), and [hyperlinks](http://www.ucsf.edu) (put the linked text in square brackets immediately followed by the address in parens, like: `[hyperlinks](http://www.ucsf.edu)`). See [this cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for more details; you can also check out the markdown in this README file by opening [winstonchiong.github.io/README.md](https://github.com/winstonchiong/winstonchiong.github.io/blob/master/README.md) and clicking "Raw."
3. **YAML**. YAML is a structured data format that uses space-indents (no tab-indents!) to show structure and colons to associate fields and values. For example:
    ```
    - name: Alex Beagle
      position: Medical Student
      email: alex.beagle (at) ucsf.edu
    - name: Julia Heunis
      position: Medical Student
      email: julia.heunis (at) ucsf.edu
    - name: Carson Quinn
      position: Medical Student
      email: carson.quinn (at) ucsf.edu
    ```
    This list has three entries. Each entry has fields for name, position, and e-mail address. Note that you don't have to put strings within quotation marks, although sometimes this is helpful if your string has special characters like colons or quotation marks. You can also often embed Markdown code like asterisks in these strings. 
    
## How to update (or add) a team profile
Two steps:
### If you don't have one yet, add a picture to /assets/img/
A good size for team member pictures on this site is 580x580 pixels, in jpeg or png format. Name your picture file something descriptive that won't be mistaken for any other image on the site (like your_name.jpg). Navigate to [/assets/img/](https://github.com/winstonchiong/winstonchiong.github.io/tree/master/assets/img) and drag-and-drop the picture file from your desktop into the browser window. You'll then be asked to make a "commit":

![Screenshot-commit-image](/assets/img/site_readme_02_commit_image.png)

In the box below **Commit changes**, instead of "Add files via upload" type in a more informative description like "upload YOUR FILENAME for members.yml" and click the green button to commit the file directly to the master branch.

### Edit the team member data in the YAML file /_data/members.yml
Navigate to /_data/members.yml and click the pencil for "Edit this file":

![Screenshot-edit-members](/assets/img/site_readme_01_edit_data_members.png)

If you already have a profile, you'll see fields for your name, degrees, position, e-mail address and so forth. E.g.:

```
- name: Ali Zahir
  image: AliZahir.jpg
  altimage: 
  position: Research Coordinator
  email: ali.zahir (#!) ucsf.edu
  scholar: 
  twitter: 
  description: Ali, a clinical research coordinator working for Dr. Winston Chiong, currently oversees 
              the coordination of a number of studies which center around decision-making in the aging brain, 
              with a particular focus on how brain structures involved in financial and medical decisions are...
```
If you don't yet have a profile, you'll need to create a new one roughly matching the format of the existing entries. (The entries will be displayed on the site in the same order that they are here, so put yours in the appropriate place.) Each entry begins with a hyphen and a space, and then each subsequent part of that entry needs to be preceded by at least two spaces. If you added a picture in the previous step, type in the filename you assigned it after "image: ". Not every field needs to be filled in, e.g. if you don't have or don't want to list a twitter account. After "description: " give yourself a quick bio. Feel free to write in the first person, include something about how you've gotten interested in neuroscience or working with patients, and maybe something about yourself outside of work. Three carriage returns makes a new paragraph, as long as the new paragraph is indented to the same degree. 

At the bottom of the page you'll see another **Commit changes** box. In the box below, you can write something like "Update members.yml to include YOUR NAME" and click the green button to commit the file directly to the master branch. 

After you commit, it might take a minute or two to see these changes reflected in the "team" page, and you might need to refresh your browser. 

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
