# Environment Setup

- DS-Flex 07-2021
- 07/20/21


## Learning Objectives

- [ ] Walk Through Environment Setup
- [ ] Walk Through `nbextensions` Setup
- [ ] Discuss installing a code editor (like VS Code or SublimeText).
- [ ] Discuss GitHub Desktop: https://desktop.github.com/
- [ ] Go over the general workflow for tackling labs on Illumidesk and in your local environment

# Environment Setup

## Env Setup Lessons

There are 2 lessons on Canvas that you will cover environment installation:

1. **OS-Specific Set-Up Lessons:**
    - Setting up a Professional Data Science Environment - MacOS
        - [Canvas Link](https://learning.flatironschool.com/courses/4339/pages/setting-up-a-professional-data-science-environment-macos-installation?module_item_id=276027)
        - [Repo Link](https://github.com/learn-co-curriculum/dsc-data-science-env-mac-installation)
    - Setting up a Professional Data Science Environment - Windows Installation
        - [Canvas Link](https://learning.flatironschool.com/courses/4339/pages/setting-up-a-professional-data-science-environment-windows-installation?module_item_id=276029)
        - [Repo Link](https://github.com/learn-co-curriculum/dsc-data-science-env-windows-installation)
    
2. **Setting up a Professional Data Science Environment - Configuring Git and Anaconda**
    - [Canvas Link](https://learning.flatironschool.com/courses/4339/pages/setting-up-a-professional-data-science-environment-configuring-git-and-anaconda?module_item_id=276031)
    - [Repoo Link](https://github.com/learn-co-curriculum/dsc-data-science-env-config)
    



### 👨‍🏫 Environment/Tools Slide Show

- **There is also a Central Lecturer recording in Topic 01**: 
    - [**🎬 Video: Data Science Environments** [Central Lecturer Lesson]](https://learning.flatironschool.com/courses/4339/pages/video-data-science-environments?module_item_id=276038)
- Environment/Tools Slide Show: 
    - [Flatiron Tools: Illumidesk and Your Local Environment Slides](https://docs.google.com/presentation/d/1RKgrPf99l7m5r0dRvPp4nFzQQ9NgpA082boj7nvzx4M/edit?usp=sharing)


### Question to the group:

- Who has already taken a stab at installing their environment?
    - Success?
    - Errors?

- Anyone (especially windows users) getting an error every time their terminal starts about conda init? 

##  👨‍🏫  Walk-Through Environment Set-Up

    
2. **Setting up a Professional Data Science Environment - Configuring Git and Anaconda**
    - [Canvas Link](https://learning.flatironschool.com/courses/4339/pages/setting-up-a-professional-data-science-environment-configuring-git-and-anaconda?module_item_id=276031)
    - [Repo Link](https://github.com/learn-co-curriculum/dsc-data-science-env-config)

## Environment Setup Troubleshooting:  What if...

### "learn-env" doesn't show up in your list of jupyter notebook kernels?

1. Make sure that had activated your `learn-env` before booting up your notebook server.
2. Make sure that you had entered the following command in your terminal after installing your learn-env
```bash
  python -m ipykernel install --user --name=learn-env```

### Your terminal doesn't activate learn-env automatically


-  Enter the following command into your terminal (Windows Users replace `conda activate` with `source activate`)<br>
```bash
echo "conda activate learn-env" >> ~/.bash_profile```


### You have a mac that displays a message about the default shell being zsh

- [Original Source URL](https://www.howtogeek.com/444596/how-to-change-the-default-shell-to-bash-in-macos-catalina/)
    - From your terminal, run this command:
```bash
chsh -s /bin/bash
```
- To silence the warning message about the default shell has changed, add this command to your `~/.bash_profile`
 ```bash
 export BASH_SILENCE_DEPRECATION_WARNING=1
 ```


### I have a new Mac with an M1 chip?

- I **think** you should be okay with setting up your environment.
- I found [this blog post that you may find helpful](https://vineethbharadwaj.medium.com/setting-up-anaconda-navigator-spyder-jupyter-python-environments-on-macbook-with-m1-chip-for-2a4b9849c1ec)

- While we don't use it until phase 4, here are some guides on install `tensorflow` on the M1 macs:
    - Article: https://www.ai-buzz.com/18-steps-to-install-tensorflow_macos-on-m1-macbook-2020/
    - Video: https://youtu.be/W_Qbrnp6uis

# ✅ Install a Code Editor

- When dealing with code, the default text editing applications included in Windows and MacOS are not ideal (especially on Mac).

#### You should install one or the other (or both!) of the following:
- [ ] [SublimeText](https://www.sublimetext.com/)
    - Great lightweight text editor with some convenient features. 
    - [Official Anaconda Guide on setting up SublimeText](https://docs.anaconda.com/anaconda/user-guide/tasks/integration/sublime/)
- [ ] [VSCode](https://code.visualstudio.com/)
    - Great more full-featured text editor that is bordering on being an IDE (integrated development environment)
    - [Official Anaconda Guide on setting up VSCode](https://docs.anaconda.com/anaconda/user-guide/tasks/integration/python-vsc/)

###  Once you've installed a code editor:

- [ ] Check out your ~/.bash_profile (**we will discuss your .bash_profile again as part of topic 02: bash and git**)


- **BONUS HACK:** Add a "jnb" shortcut that allows you to type `jnb` to open jupyter notebook.
- Add:
  ```alias jnb="jupyter notebook" to your .bash_profile```
  
  - Note: if you are using a different shell besides bash, you will need to find out its equivalent of `.bash_profile` (e.g. .zschrc)
  

# ✅ Install Jupyter Notebook Extensions

### Jupyter Notebook Extensions Resources

- [Documentation](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/)
    
-  [Study Group Video](https://youtu.be/Fl7Xwr_kUkw)

###  Installation & activation
- [Official `nbextensions` Documentation](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html)


- **The best way to install is via `conda`**
    0. Open your terminal and make sure learn-env is activated.

    1. Install the extensions via conda
    ```bash
      conda install -c conda-forge jupyter_contrib_nbextensions
      ```

    2. Activate the extension configurator
    ```bash
    jupyter nbextension enable jupyter_nbextensions_configurator
      ```
      
- **If you have issues installing with conda, install with pip instead:**
    1. Install extensions
    ```bash
    pip install jupyter_contrib_nbextensions
    ```
    2. Install additional requirements (Install javascript and css file):
    ```bash
    jupyter contrib nbextension install --user
    ```
    3. Activate the extension configurator
    ```bash
    jupyter nbextension enable jupyter_nbextensions_configurator
      ```

### Turning on extensions

- **When you boot up jupyter notebook, there should be a new tab at the top called `nbextensions`.** Click on the tab to open the list of available extensions.


- This opens a menu of all of the available extensions with checkboxes to activate them; 
  - ***NOTE: If the list of available notebook extensions is grayed out:***
    - Uncheck "`disable configuration for nbextensions without explicit compatibility (they may break your notebook environment, but can be useful to show for nbextension development)`" at the top of the page next to the search box.
    
    
    
- **Clicking the name of an extension will load its options menu** below the table of extensions. 

### Recommended extensions & settings



- `Table of Contents (2)`: 
    - Clickable sidebar with markdown headers as bookmarks/links.
    - Recommended options:
        - Change `Maximum level of nested sections to display on the tables of contents` to 3.
        -  Check `Display Table of Contents as a sidebar (otherwise as a floating window)`
        - Check `Collapse/uncollapse ToC sections when the collapsible_headings nbextension is used to collapse/uncollapse sections in the notebook. For the inverse behaviour, see collapsible_headings' configuration`


- `Collapsible Headings`: Collapse sections of your notebook using markdown headers.
    - Recommended options: 
        -  Check 'Collapse/uncollapse notebook sections when the ToC2 nbextension is used to collapse/uncollapse sections in the table of contents. For the inverse behaviour, see ToC2's configuration' at towards the bottom of the options.


- `Codefolding`: Lets you collapse function definitions and blocks of code. 


- `Live Markdown Preview`: Shows a preview of what the markdown cell you are editing will look like once you render it with Shift+Enter
    - Recommended options:
        - Check `Show the input & output of markdown cells side-by-side while editing them.`


- `spellchecker`

<!-- 
- `Variable Inspector` (but warning/caveat): 
    - Lets you see details about all of the variables in your notebook.
    - HUGELY helpful for new coders.
    - Recommended options:
        - `Display window at startup` (for now while you are learning python)
 -->

# 🔬Workflow for Labs 🧪

> - While you CAN work on both Illumidesk and your local computer, I recommend using your local computer for a few reasons:
    - You will have to do the Key Cumulative Labs for each phase on your local computer. 
    - You will get more activity added to your GitHub user profile (the green boxes on your profile page)

## On Illumidesk

- Any code done on Illumidesk will be saved to Illumidesk ONLY.
- In order to save your labs, you will need to follow the instructions on this repo's README: 
    - https://github.com/learn-co-curriculum/dsc-saving-illumidesk-work-to-github
    


## On Your Local Machine

- From Canvas page:(not illumidesk notebook) click on the GitHub icon <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width=30px style="display:inline"> which will open the repo on GitHub.com
- Click on the `Fork` button and copy the url for your fork.
<!-- - Clone lesson to your PC. -->
- Open terminal, navigate to the folder where you want the repo to appear. 
    - e.g. `cd ~/Documents/Flatiron/Phase_1/`
- Clone your fork using the URL you copied from github.
    `git clone <url-of-your-fork>`

- From your terminal, `cd` into the cloned repo's folder.
- Launch jupyter notebook with terminal.
    - `jupyter notebook`


- Complete the lab.
- Save & checkpoint notebook


- Either open a new terminal in the same folder as your repo
    - OR shut down jupyter (using the `Quit` button or `Cntrl+C`) and use the terminal that was running your notebook.
 

#### Save your completed lab by running the following commands


- To save your updated repo:

```bash
## cd to base folder of repo
cd path/to/repo

## Add changes to commit
git add .
# Commit the changes with a  message
git commit -m "your message here"
# Push changes to GitHub profile
git push
```

- Note, you can actually accomplish steps 2 and 3 above in one line of code with 
```bash
git commit -am "message"
git push
```

# 📜Appendix:

## GitHubDesktop

- Consider installing [GitHub Desktop](https://desktop.github.com/)
<img src="https://desktop.github.com/images/github-desktop-screenshot-mac.png" width=50%>

## Showing Hidden Files

- Windows Users: 
    - Turn on View Hidden Files and Folders in your File Explorer menu:
        - [Microsoft Support Article](https://support.microsoft.com/en-us/windows/view-hidden-files-and-folders-in-windows-10-97fbc472-c603-9d90-91d0-1166d1d9f4b5#:~:text=Open%20File%20Explorer%20from%20the,folders%2C%20and%20drives%20and%20OK.)
        
    - On the same settings page, also deselect "Hide extensions for known file types and click OK."
    
    
- Mac Users:
    - Use this keyboard shortcut from inside finder:
    `Cmd+Shift+.`
    - Use it again to hide hidden files. 
