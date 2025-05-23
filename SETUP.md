### Local Setup

##### Installation
```bash
brew install node
sudo chown -R 501:20 "/Users/himanshujain/.npm"
npm install -g n
sudo n latest
sudo n prune
sudo npm install -g npm@latest
brew install pnpm
pnpm update
brew install corepack
pnpm view @astrojs/check version
pnpm view astro version
pnpm view firebase-tools version
pnpm view hotkeypad version
pnpm view typescript version

❯ node -v
v23.11.0
❯ npm -v 
11.3.0
❯ n --version
v10.1.0
❯ pnpm -v
10.8.0
```

##### Enable pnpm
```bash
--- RUN THIS ONLY ---
corepack enable pnpm
corepack prepare pnpm@latest --activate
pnpm install


--- Once dev is completed ---
corepack disable pnpm
```

##### Build / Run the project
```bash
pnpm build -> debug
pnpm dev -> run locally [Use this while developement]
pnpm preview -> See the final results
```

##### Update dependencies in package.json
```bash
pnpm outdated
```

##### Vulnerabilities
```bash
pnpm audit
pnpm audit --fix
pnpm install
```

#### Firebase  (First time only)
```bash
https://docs.astro.build/en/guides/deploy/google-firebase/

pnpm exec firebase login
pnpm exec firebase experiments:enable webframeworks

❯ pnpm exec firebase init hosting
(node:78290) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

You're about to initialize a Firebase project in this directory:

  /Users/himanshujaindev/Documents/MyProject/himanshujain.dev


=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add, 
but for now we'll just set up a default project.

? Please select an option: Use an existing project
? Select a default Firebase project for this directory: himanshujain-dev (himanshujain-dev)
i  Using project himanshujain-dev (himanshujain-dev)

=== Hosting Setup
? Detected an existing Astro codebase in the current directory, should we use this? Yes
? In which region would you like to host server-side content, if applicable? us-west1 (Oregon)
? Set up automatic builds and deploys with GitHub? Yes

i  Detected a .git folder at /Users/himanshujaindev/Documents/MyProject/himanshujain.dev
i  Authorizing with GitHub to upload your service account to a GitHub repository's secrets store.

Visit this URL on this device to log in:
https://github.com/login/oauth/authorize?client_id=89cf50f02ac6aaed3484&state=468433298&redirect_uri=http%3A%2F%2Flocalhost%3A9005&scope=read%3Auser%20repo%20public_repo

Waiting for authentication...

✔  Success! Logged into GitHub as himanshujaindev

? For which GitHub repository would you like to set up a GitHub workflow? (format: user/repository) himanshujaindev/himanshujain.dev

✔  Created service account github-action-758416389 with Firebase Hosting admin permissions.
✔  Uploaded service account JSON to GitHub as secret FIREBASE_SERVICE_ACCOUNT_HIMANSHUJAIN_DEV.
i  You can manage your secrets at https://github.com/himanshujaindev/himanshujain.dev/settings/secrets.

? Set up the workflow to run a build script before every deploy? No

✔  Created workflow file /Users/himanshujaindev/Documents/MyProject/himanshujain.dev/.github/workflows/firebase-hosting-pull-request.yml
? Set up automatic deployment to your site's live channel when a PR is merged? No

i  Action required: Visit this URL to revoke authorization for the Firebase CLI GitHub OAuth App:
https://github.com/settings/connections/applications/89cf50f02ac6aaed3484
i  Action required: Push any new workflow file(s) to your repo

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...

✔  Firebase initialization complete!

pnpm exec firebase deploy --only hosting
```

### GitHub Actions 
<img width="702" alt="image" src="https://github.com/user-attachments/assets/383c0459-176f-4a57-aee7-a5043cb6de14" />



### pnpm build
```
❯ pnpm build

> minimalist-portfolio-json@0.0.1 build /Users/himanshujain/Documents/projects/github.com/himanshujaindev/himanshujain.dev
> astro check && astro build

19:28:46 [content] Syncing content
19:28:46 [content] Synced content
19:28:46 [types] Generated 21ms
19:28:46 [check] Getting diagnostics for Astro files in /Users/himanshujain/Documents/projects/github.com/himanshujaindev/himanshujain.dev...
Result (48 files): 
- 0 errors
- 0 warnings
- 0 hints

19:28:48 [content] Syncing content
19:28:48 [content] Synced content
19:28:48 [types] Generated 15ms
19:28:48 [build] output: "static"
19:28:48 [build] mode: "static"
19:28:48 [build] directory: /Users/himanshujain/Documents/projects/github.com/himanshujaindev/himanshujain.dev/dist/
19:28:48 [build] Collecting build info...
19:28:48 [build] ✓ Completed in 21ms.
19:28:48 [build] Building static entrypoints...
19:28:49 [vite] ✓ built in 379ms
19:28:49 [build] ✓ Completed in 393ms.

 building client (vite) 
19:28:49 [vite] ✓ 3 modules transformed.
19:28:49 [vite] dist/_astro/KeyboardManager.astro_astro_type_script_index_0_lang.DQNrSzZY.js  9.50 kB │ gzip: 3.56 kB
19:28:49 [vite] ✓ built in 14ms

 generating static routes 
19:28:49 ▶ src/pages/index.astro
19:28:49   └─ /index.html (+6ms) 
19:28:49 ✓ Completed in 8ms.

19:28:49 [build] 1 page(s) built in 443ms
19:28:49 [build] Complete!
```