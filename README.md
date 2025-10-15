# psy3019.github.io
Site officiel du cours PSY3019 Traitement de données en neurosciences cognitives

The codebase of this website is licensed under a
[MIT License][mit] and is based on the [Myst Markdown](https://mystmd.org/) framework.

## Usage

### Building the book

If you'd like to develop and/or build the psy3019 website, you should:

1. Clone this repository
2. Run `pip install -r content/requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `content/` directory
4. Run `myst build --html` to create the website

A fully-rendered HTML version of the book will be built in `_build/html/`. If a change is merged into `main`, a github action will automatically publish an updated version of the website.

## Contributors

We welcome and recognize all contributions. You can see a list of current contributors in the [contributors tab](https://github.com/psy3019/psy3019.github.io/graphs/contributors).

Note that the content of the modules have been created collaboratively by the brainhack community. See this [repository](https://github.com/school-brainhack/school-brainhack.github.io) for details of contributions.

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).


## 📦 Importing the `modules` folder from School Brainhack website

This repository includes the `content/en/modules` folder from
[`school-brainhack/school-brainhack.github.io`](https://github.com/school-brainhack/school-brainhack.github.io)
as a **Git subtree**, allowing us to sync updates both ways while keeping a clean, self-contained history.

---

### 🧩 1. One-time setup — add the subtree

Run this from the root of your repository:

```bash
git remote add school-brainhack https://github.com/school-brainhack/school-brainhack.github.io.git
git fetch school-brainhack main
git subtree add --prefix=content/en/modules school-brainhack main --squash
```

This copies the `content/en/modules` directory from the `main` branch of the School Brainhack site into your repo, squashing its history into a single commit.

---

### 🔄 2. Pulling updates from upstream

When the upstream folder changes, bring those changes into your repo with:

```bash
git fetch school-brainhack main
git subtree pull --prefix=content/en/modules school-brainhack main --squash
```

This performs a standard three-way merge.
If there are conflicts, Git will guide you to resolve them in `content/en/modules`.

---

### 🚀 3. Pushing your local edits back upstream

If you’ve made improvements in `content/en/modules` that should be merged into the School Brainhack website:

```bash
git subtree push --prefix=content/en/modules school-brainhack main
```

That will create a branch in the remote repo (if you have write access).
If you don’t, you can push it to your fork:

```bash
git remote add myfork https://github.com/<your-username>/school-brainhack.github.io.git
git subtree push --prefix=content/en/modules myfork my-updates
```

Then open a pull request on GitHub.

---

### 🧰 4. Common maintenance tips

* Always run `git fetch school-brainhack` before pulling or pushing.
* Use `--squash` unless you explicitly need full history (saves space and keeps logs clean).
* Keep local edits minimal and compatible with upstream structure to reduce merge conflicts.

---

### 💡 5. Quick summary

| Action       | Command                                                                       |
| :----------- | :---------------------------------------------------------------------------- |
| Add subtree  | `git subtree add --prefix=content/en/modules school-brainhack main --squash`  |
| Pull updates | `git subtree pull --prefix=content/en/modules school-brainhack main --squash` |
| Push changes | `git subtree push --prefix=content/en/modules school-brainhack main`          |

---

Maintainer note:
`git subtree` is simpler than submodules — it embeds the files directly in your repo, so cloning this project automatically includes the `modules` folder with no extra steps.
