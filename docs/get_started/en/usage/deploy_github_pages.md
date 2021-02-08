---
title: Deploy the website generated by teedoc to github pages
keywords: teedoc, deployment
desc: Deploy the website generated by teedoc to the server
---



## Clone the template warehouse

Visit [https://github.com/teedoc/teedoc.github.io](https://github.com/teedoc/teedoc.github.io)
Click `Use this template`
![github use template](../../assets/images/github_use_template.jpg)
Then fill in the new warehouse name (the warehouse name is preferably `teedoc.github.io` and replace `teedoc` with your user name or organization name) and description. Create a new warehouse of your own based on this warehouse, and now you have it The warehouse is exactly the same as the official website of `teedoc`
> You will find a directory of `.github/workflows`, this is the configuration file of `github action`, we use this function to achieve:
> When we update the source file of the warehouse, `github action` automatically builds and generates static web pages according to the commands of this configuration file, and then pushes to the `gh-pages` branch of this warehouse

## Generate ssh key

Then generate a pair of `key` locally (relevant software needs to be installed under windows, please install it yourself (you will have it if you install git))
```
ssh-keygen -t rsa -f key.txt
```
Got the two files `key.txt` and `key.key.pub`

## Set key

Set the `ssh` key in the settings of the document project, add a `ssh` key, copy the content in `key.txt.pub`, pay attention to the `pub` file, which is the public key, and take whatever name you want
![](../../assets/images/github_deploy_key.jpg)

Then click `Secrets` to set secret key-value pairs. The variables that need to be set are:
* `ACCESS_KEY`: Copy the content in `key.txt`
* `GIT_EMAIL`: Set a `git` submission email, just set your `github` email
* `GIT_NAME`: Set a `git` commit name, just set your `github` name
* `REPO`: warehouse address, set to `organization name/warehouse name` or `user name/warehouse name`, such as `teedoc/teedoc.github.io`
![](../../assets/images/github_secrets.jpg)


## Trigger build

Like a warehouse submitting a modification, the build will be triggered automatically. You can see the progress and logs in the `Actions` column

If it is a green tick, it means a success, otherwise it means a failure. You can click in to see what errors are reported in the build log. Generally, the previous value is filled in wrong

![](../../assets/images/github_action.jpg)

## Set up pages service

Then find the `pages` service setting in the settings, open it, and then visit the corresponding domain name,
For example, here is `https://teedoc.github.io/`

>! Note that if the following path is not `/` and there is no custom domain name, such as `https://teedoc.github.io/my_site/`, you need to configure `"site_root_url":"/ in `site_config.json` my_site/"`

![](../../assets/images/github_pages.jpg)