# Cookiecutter howto

## Ant/Java

The DSE-Static-Cookiecutter relies on Ant/Java. Check [this howto](ant_howto.md) if you didn't install them yet.

## Recommended: use uv

If `uv` is available, this is the easiest method because it runs cookiecutter without a permanent install.

1. Open a terminal (`cmd`, PowerShell, or shell).
2. Run:

```bash
uvx cookiecutter gh:acdh-oeaw/dse-static-cookiecutter
```

3. Answer the questions from cookiecutter.
4. Enter the generated project folder.

## Fallback: use pip

If `uvx` is not available, install and run cookiecutter with Python/pip.

1. Check Python first:

see [python howto](python_howto.md)

2. Install cookiecutter:

```bash
python -m pip install --user cookiecutter
```

On Linux/macOS, if needed:

```bash
python3 -m pip install --user cookiecutter
```

3. Run cookiecutter from GitHub:

```bash
python -m cookiecutter gh:acdh-oeaw/dse-static-cookiecutter
```

On Linux/macOS, if needed:

```bash
python3 -m cookiecutter gh:acdh-oeaw/dse-static-cookiecutter
```

4. Answer the questions and enter the generated project folder.

## Quick troubleshooting

- `uvx: command not found`: use the pip fallback above.
- `No module named pip`: run `python -m ensurepip --upgrade` and try again.

## Answering the questions during install

Read the texts. Decide then. The answers in brackets are the default answers. Press enter to accept them.
* `[7/12] The URL you have reserved for your website.` -> just go with the dafault if you don't know what that means.
* `[8/12] The ID of the Redmine-Service-Issue for you application. This is needed to generate an up do date imprint (18716):` ->  Just press enter if you aren’t working for the ACDH. Otherwise you'll know what to do.
* `[9/12] Should i18n be included to provide translations` -> if this is just a simple install for a seminar etc. the answer is "1" (no)
*  `[10/12] Ideally data and code is separated. If you want to use the code repo to store/curate the data as well, type 'no' …` -> just type "n" and press enter
* after that just confirm the defaults by pressing enter

## Setting up the basic install
1. open a terminal in the folder you created. Don't know what that is? Have a look [here](shell_crash_course.md).
   - on Windows, you can open `cmd` or PowerShell first and then change into the folder with `cd`
   - in your file browser, right-click the folder and choose something like `Open in Terminal`
   - in VS Code, right-click any file or folder in the project and choose `Open in Integrated Terminal`
   - if you already have a terminal open, use `cd` to move into the project folder before continuing
2. in the terminal type ```ant``` and hit enter. It will print some text and ```BUILD FAILED```. Don't worry about that.

## Fiddling with the errors
So will run into a few errors, since your project ist missing some parts. The ACDH provides an imprint service for its projects. Since you are not part of the ACDH, you can't use it. You will thus see an error like: 
   ```
   BUILD FAILED
   …
   …data/imprint.xml does not exist
   ```
   Open your build.xml file in the root dir of your project.
   Make the xslt-step starting with the line ```<xslt in="./data/imprint.xml" out="${target}/imprint.html" style="./xslt/imprint.xsl">``` as a commentary by putting ```<!--``` in front and ```-->``` at the end of it. Do the same for the step starting with ```<xslt in="./data/imprint.xml" out="${target}/api.xml" style="./xslt/api.xsl">``` 

   Rerun ant. It should work now. Remember to set up an impressum page, if you ever want to publish your project online. You can easily do so by creating the index.xml by hand. Have a look at the responsible xslt script to understand, what data/structures are required.

