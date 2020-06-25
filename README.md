<p align="center">
  <a href="http://lovera.maxam.now.sh/">
    <img src="https://user-images.githubusercontent.com/25841814/79395484-5081ae80-7fac-11ea-9e27-ac91472e31dd.png" alt="screenshot" width="500">
  </a>
  <h3 align="center">📌✨productive-box</h3>
</p>

<p align="center">
   <img src="https://img.shields.io/badge/language-typescript-blue?style"/>
   <img src="https://img.shields.io/github/license/maxam2017/productive-box"/>
   <img src="https://img.shields.io/github/stars/maxam2017/productive-box"/>
   <img src="https://img.shields.io/github/forks/maxam2017/productive-box"/>
</p>
<p align="center">
   Are you an early 🐤 or a night 🦉?
   <br/>
   When are you most productive during the day?
   <br/>
   Let's check out in gist!
</p>

---

> This project is inspired by an awesome pinned-gist project.<br/>Find more in https://github.com/matchai/awesome-pinned-gists

## Overview
This project uses GitHub graphQL API to get the commit histories and write into the gist by [rest.js](https://github.com/octokit/rest.js#readme)

## Setup
Description is modified to be more detailed.

1. Create a new public GitHub Gist at https://gist.github.com/.

  - Keep this new Gist empty. You don't have to fill any info in it.
  - Once the gist is created, copy only the gist ID from the url, ie: `https://gist.github.com/maxam2017/`**`9842e074b8ee46aef76fd0d493bae0ed`**.
  - The idea of Gist here is that everytime the script runs a scheduled cron job, it reads in the repo activities onto the Gist.  


2. Create a token at https://github.com/settings/tokens/new.

  - Copy the generated token ID. This will be used in step 6.

  - Select `gist` and `repo` scope, and create it.  
   > enabling `repo` scope seems **DANGEROUS**<br/>
   > but this GitHub Action only accesses your commit timestamp in repository you contributed.

3. Fork this repo

4. Go to your forked repository > Settings > Secrets, and create two variables.

5. Name the first one as "GIST_ID" and fill in the value as the gist ID you copied from step 1

6. Create a second one as "GH_TOKEN" and fill in the value as the token ID you copied from step 2.

7. In the "Repository" tab, navigate and open `.github/workflows/schedule.yml` and edit the two followings:

  - **GIST_ID:** Replace with your Gist ID from step 1
  - **TIMEZONE:** The timezone of your location, eg. `Asia/Taipei` for Taiwan, `America/New_York` for America in New York, etc.


8. Open the "Actions" tab, and click the "enable" button. You don't have to do anything further.

9. [Pin the newly created Gist](https://help.github.com/en/github/setting-up-and-managing-your-github-profile/pinning-items-to-your-profile)

10. Wait until the cron job is run (default is set to 0 0 0),  
or you can make a push in the forked repo, which will update the gist.
