
1. Install `conda` (miniconda) from [here](https://docs.anaconda.com/miniconda/).
   1. We're choosing miniconda as it's a lightweight version of anaconda.
2. `conda create -p ./.conda python=3.11`
   1. As conda allows inclusion of a dedicated python version during creation, while `venv` [doesn't](https://ericmjl.github.io/data-science-bootstrap-notes/install-anaconda-on-your-machine/#:~:text=Manage%20different%20Python%20versions%20into%20isolated%20environments%20using%20a%20consistent%20interface).
3. `conda activate ./.conda`
   1. To activate the created conda environment.
4. `pip --version` 
   1. To check pip's path and make sure that you're using pip which is inside the activated conda environment.
5. `pip install -r requirements.txt`
   1. Note: Even though `ffmpeg-python` is mentioned in the requirements file, you may still receive a "No module named 'ffmpeg' error". In that case, you can install it on pc-level via download links mentioned [here](https://docs.manim.community/en/stable/installation/windows.html#manual-installation) (Or, just [conda install](https://docs.manim.community/en/stable/installation/conda.html) manim instead).
   2. (Totally optional) You can use `pip-install` command instead, by first getting my custom PowerShell configuration from [this](https://gist.github.com/OdyAsh/3996afd93c2d9ee4850dc0ca4cbed14f) gist.
   3. This command will automatically add each manually installed package to `requirements-*.txt` files, which should help you [not entirely rely on](https://builtin.com/software-engineering-perspectives/pip-freeze) `pip freeze`.
   4. Side note: one might ask, why not use `pipreqs` library mentioned in above link? Because `pipreqs` "only puts those libraries in the requirements file which have been used in the project through imports.". However, some libraries might not be imported directly, but are still required for the project to run (e.g., I think we never directly import ffmpeg, yet we need it,). Therefore, I believe the safest way is to [manually add each package to the requirements file](https://blog.alexo.dev/posts/2021-06-13-avoid_pip_freeze/#:~:text=you%E2%80%99re%20at%20least%20verifying%20that%20your%20requirements%20file%20isn%E2%80%99t%20just%20broken%20if%20you%20happen%20to%20hand%20it%20off%20to%20another%20team%20or%20individual)... which is what I'm doing with my custom command :].
