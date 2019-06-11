# cloud-reno-test

This a test repo from reno notes. There are lots of things happneningna here and; 'nora is going a to acorretc me.

## Creating a release note

1. Clone the repository:

   `$ git clone git@github.com:asettle/cloud-reno-test.git`

2. Install `reno` and `tox`:

  ```
  $ sudo zypper in python3-pip python3-devel
  $ sudo pip install reno tox
  ```

  (If you're inclined to use openSUSE's packages instead of `pip`-supplied ones,
  read the *Side Notes* section at the bottom.)

3. You can now create a release note. Check out a branch:

   `$ git checkout -b <BRANCHNAME>`

   **IMPORTANT:** Ensure you are in the root directory of your Reno local repo
   before you create a note or it will duplicate all of the relevant subtree.

4. Run the following command to create a release note:

   `$ reno new <RELEASE-NOTE-NAME>`

   You will receive the following output:

   `Created new notes file in releasenotes/notes/<RELEASE-NOTE-NAME>-<RANDOMNUMBERGENERATION>.yaml`

5. Open the release note and edit in your choosen text editor. A template is used with the following titles:

   - feature
   - issue
   - upgrade
   - deprecation
   - critical
   - security
   - fixes
   - other

   Edit the template to include *only* the section(s) you want to use.

6. Save the file.

7. Check for common syntax issues by running `reno lint`. If you get a Python
   traceback, there is something wrong with your note.

8. Add to the commit:

   `$ git add releasenotes/notes`

9. Commit your change:

    `$ git commit -a -ma "MY MESSAGE HERE"`

10. Push back up to GitHub:

   `$ git push`

11. Have someone (asettle) review your PR quickly to ensure there are no breaks.
    Once that is complete, move to the next steps.

## Building release notes

To build the release notes, ensure your local copy is up to date:

`$ git pull origin master`

Run the following tox command:

`$ tox -e releasenotes`


## Side Notes

* If you only want to add new notes via Reno, you can also install the
  openSUSE packages `python3-reno` and `python3-pbr`. However, to build
  an output document, `python3-tox` is necessary in addition and this dependency
  is currently not recent enough in openSUSE Leap 15.1.
