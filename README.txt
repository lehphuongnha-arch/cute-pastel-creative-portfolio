# Cute Pastel Creative Portfolio + Decap CMS

This package replaces the current demo `index.html` with a CMS-ready pastel portfolio and adds the Decap CMS admin page.

## Files
- `index.html`: website reads portfolio data from `content/portfolio.json`
- `admin/index.html`: CMS interface
- `admin/config.yml`: CMS configuration for the GitHub repository
- `content/portfolio.json`: editable homepage copy, skills, and project list
- `images/uploads/`: folder where CMS uploads images

## Before logging in to /admin/
The GitHub backend needs OAuth authentication. Do not put a GitHub personal access token or OAuth client secret in this repository.

1. In GitHub, create a **new OAuth App** in Settings > Developer settings > OAuth Apps.
2. Homepage URL: `https://elegant-treacle-121093.netlify.app`
3. Authorization callback URL: `https://api.netlify.com/auth/done`
4. Register the app. Copy the Client ID and generate a Client Secret.
5. In Netlify, open this project and find Project configuration > Access & security (or Security) > OAuth / Authentication providers. Install/configure the GitHub provider using the Client ID and Client Secret. Keep the secret private.
6. After uploading these files and waiting for the deploy, open `https://elegant-treacle-121093.netlify.app/admin/` and sign in with the GitHub account that has write access to the repository.

Netlify menu names may vary. If you cannot find the OAuth provider settings, stop and ask for help before creating additional apps.

## Upload through GitHub without writing code
1. Open the repository and click **Add file > Upload files**.
2. Extract this ZIP on your computer first.
3. Upload the `index.html` file to the repository root. It will replace the current demo homepage.
4. Upload the folders `admin`, `content`, and `images` by dragging their contents/folders into GitHub's upload area. Make sure the final repository paths are exactly `admin/index.html`, `admin/config.yml`, `content/portfolio.json`, and `images/uploads/.gitkeep`.
5. Commit directly to `main`, then wait for Netlify to deploy.
6. Test the homepage first, then visit `/admin/`.

## Editing
In `/admin/`, open **Portfolio Content > Homepage & Projects**. Update your name, intro, About Me, email, skills, project descriptions, links, and project images. Add or remove items in the Projects list, then publish/save. A new image can be uploaded through the image field.

The starter content includes project descriptions based on the existing portfolio links and a Jettribe trophy project. Check every description and add the real project images before treating the site as final.

## Important
- This is a static website; adding a project through CMS updates the JSON file and Netlify redeploys automatically.
- Do not upload GitHub OAuth Client Secret or any access token into the repository.
- The CMS will not allow sign-in until the GitHub OAuth provider is configured in Netlify.
