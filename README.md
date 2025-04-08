name: Buildozer Android APK Build

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      - name: Install dependencies
        run: |
          sudo apt-get update
          sudo apt-get install -y libffi-dev libssl-dev build-essential python3-pip git zip unzip openjdk-11-jdk
          python3 -m pip install --upgrade pip
          pip install buildozer cython virtualenv

      - name: Build APK
        run: |
          cd ./ # yaha tu apne source code ka path de, filhaal same hai
          buildozer android debug

      - name: Upload artifact
        uses: actions/upload-artifact@v3
        with:
          name: jarvis-app
          path: bin/*.apk
          - 👋 Hi, I’m @sushiljarvis
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
sushiljarvis/sushiljarvis is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
