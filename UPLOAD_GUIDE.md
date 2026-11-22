# GitHub publishing guide

## 1. Before publishing

- The notebook copy in this pack has the embedded Roboflow credential replaced with an environment-variable lookup.
- **Revoke/regenerate the Roboflow API key that was present in the original uploaded notebook.** Treat it as exposed, even though the public copy has been redacted.
- Do not put Anthropic, Roboflow, or any other API key in HTML, JavaScript, notebooks, screenshots, video, or Git history.
- Review dataset terms before uploading any images or dataset files.
- Do not upload private research material or data you do not have permission to redistribute.

## 2. Create the repository

1. Sign in to GitHub and choose **New repository**.
2. Repository name: `coffeevision`.
3. Suggested description: `AI-assisted experimental prototype for coffee cherry ripeness classification and coffee bean quality assessment.`
4. Choose Public only if you are comfortable making the code public and have checked dataset/code permissions.
5. Do not initialise with a README if you plan to upload this complete pack (the pack already contains one).

## 3. Upload through the GitHub website

1. Open the new repository.
2. Choose **Add file → Upload files**.
3. Extract this ZIP on your computer.
4. Drag the contents of the `CoffeeVision-portfolio-pack` folder into the GitHub upload area.
5. Commit with message: `Add CoffeeVision prototype and documentation`.

## 4. Or upload with Git

Run these commands from inside the extracted `CoffeeVision-portfolio-pack` folder:

```bash
git init
git add .
git status
git commit -m "Add CoffeeVision AI-assisted prototype"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/coffeevision.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.

## 5. After publishing

- Add the GitHub URL to your CV and LinkedIn Featured section.
- Add the YouTube walkthrough URL after recording it.
- Pin the repository on your GitHub profile.
- Keep the README honest about AI assistance and unverified training.
- Update the README only after you have run the notebook and can show reproducible results.
