# Automatic compilation of Unity projects and publication on itch.io

### 📌 Description

This workflow automatically:
- Checks out the repository.
- **Cleans up disk space before building (due to GitHub Actions disk space limitations).**
- Caches Unity Library to speed up builds.
- Builds the Unity project for WebGL.
- Publishes the build to itch.io using Butler.

### 🔧 Repository Setup

1. **GitHub Secrets** (Settings → Secrets and variables → Actions):
   - `UNITY_LICENSE`: Unity license (.ulf).
   - `UNITY_EMAIL`: Your Unity account email.
   - `UNITY_PASSWORD`: Your Unity account password.
   - `BUTLER_CREDENTIALS`: Butler access token ([API Keys](https://itch.io/user/settings/api-keys)).

2. **GitHub Variables** (Settings → Variables → Repository):
   - `ITCH_USER`: Your itch.io username.
   - `ITCH_GAME`: Your game's name on itch.io (e.g., `my-game`).

3. **Add the workflow**:
   - Create a folder `.github/workflows` in the root of your project.
   - Add the file `build-and-deploy.yml` with the workflow content.

4. **Unity version**:
   - Update the `unityVersion` field in `build-and-deploy.yml` to match the Unity version used in your project.

### 🚀 Running the Workflow

- Automatically triggers on `push` to `main` branch.
- Can be run manually via GitHub Actions → Workflow → **Run workflow**.

