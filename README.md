# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:


## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

## Deployment via GitHub Actions

This project includes a GitHub Actions workflow at `.github/workflows/deploy.yml` that builds the Vite app and deploys the `dist/` folder to the `gh-pages` branch of the target repository `nandi-2006/endsemlab_33770`.

What you must do before the workflow can push:

- Create a Personal Access Token (PAT) on GitHub with the `repo` scope.
- In the repository where this workflow runs (your source repo), add a repository secret named `DEPLOY_PAT` with the PAT value.

How it works:

- The workflow installs dependencies and runs `npm run build` to produce `dist/`.
- It then pushes the contents of `dist/` to the `gh-pages` branch of `https://github.com/nandi-2006/endsemlab_33770.git` using the PAT.
- Vite's `base` setting has been updated to `/endsemlab_33770/` so assets resolve correctly when hosted under that path.

If you prefer to deploy to GitHub Pages on the same repository instead of a different repo, you can modify `deploy.yml` to push to the same repo or use actions such as `peaceiris/actions-gh-pages`.

Troubleshooting:

- Ensure the `DEPLOY_PAT` secret exists and has `repo` permission.
- Check the Actions logs for the workflow run to see build or git push errors.
