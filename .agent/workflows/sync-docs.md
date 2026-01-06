---
description: How to sync Swagger documentation to the live website
---

# Sync Swagger Documentation

To sync your backend API documentation with the live GitHub Pages website, follow these steps:

1.  **Generate Documentation**:
    In the `backend` directory, run your documentation generation script:
    ```bash
    npm run docs:generate
    ```

2.  **Sync `openapi.json`**:
    Copy the generated file to the root of the repository:
    ```bash
    cp backend/docs/openapi.json ./openapi.json
    ```

3.  **Push Changes**:
    Commit and push the updated `openapi.json` to your repository:
    ```bash
    git add openapi.json
    git commit -m "docs: update openapi.json for live website"
    git push origin main
    ```

The live website (e.g., `https://yahya.github.io/damanease-docs`) will be updated automatically!
