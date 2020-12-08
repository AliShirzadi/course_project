# Course Project Template

This file describes how to create a web site for the course cpsc4300/6300 using two approaches:

1. using mkdocs + markdown
1. using Voila + Jupyter notebook

Each team can choose their own way to create the website. However, we recommend you to use the Markdown approach since it is relatively simpler and more robust.

You can find the example at /zfs/courses/CPSC6300/web/{your-instructor's-folder}


## Create a Website using Markdown

To create a website using Markdown for the cpsc4300/cpsc6300 class to view, you can use the following process:

1. Create a subfolder named with your username within the folder /zfs/courses/CPSC6300/web:

        mkdir -p /zfs/courses/CPSC6300/web/$USER

1. Check out your course project repository into the newly created folder:

        cd /zfs/courses/CPSC6300/web/$USER
        git clone {your-project-repo}
        cd {your-project-repo-dir}
        mkdir docs
        cp report/report.md docs/index.md

1. create a mkdocs.yml file

       ```
       site_name: CPSC6300 Course Project
         nav:
           - Home: index.md
       theme: readthedocs
       ```

1. Edite the file docs/index.md to include your report.

1. Build the website

        module load courses/cpsc6300
        mkdocs build

1. Open the URL http:{your-loginvm-ip}:8080/~{your-username}/{your-project-repo-dir}/site/ in a browser to check your website.
        For example, visit [this example site](http://10.128.97.93:8080/~xizhouf/course_project/site/).

1. Commit all your project files to github

        git status
        git add docs/index.md
        git add docs/figs/*
        git add {other-files}
        git commit -m 'finalize project'
        git push

1. Add your website URL to canvas [Project signup sheet](https://clemson.instructure.com/courses/118802/pages/project-url-signup)

## Create Website using voila
 
1. Create a web folder under one of the member of the project team
 
       cd /zfs/courses/CPSC6300/web/
       mkdir -p $USER

1. Check out your project from github

       cd /zfs/courses/CPSC6300/web/$USER
       git clone {your-project-repo}
       cd {your-project-repo-dir}

1. Start Voila service in a screen session

       screen
       module load courses/cpsc6300
       voila {your-project-jupyter-notebook} --no-browser --debug

1. Check your web service at http://{your-login-vm-ip}:8866/
