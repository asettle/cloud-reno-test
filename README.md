# cloud-reno-test

This a test repo from reno notes.

## Creating a release note 

1. Clone the repository:

   `$ git clone git@github.com:asettle/cloud-reno-test.git`

2 Install reno and tox:

  ` $ (sudo) pip install reno
    $ pip install tox`
  Or
  `$ sudo zypper in python3-reno python3-pbr python3-tox`

3. You can now create a release note.

   `$ cd releasenotes`
   
   Checkout a branch:
   
   `$ git checkout -b <BRANCHNAME>`

4. Run the following commad to create a release note:
   
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

   Edit the template to include only the sections you want to use.

6. Save the file.

7. Add to the commit:

   `$ git add --all`
   
8. Commit your change:

    `$ git commit -a -ma "MY MESSAGE HERE"
    
9. Push back up to GitHub:

   `$ git push`
 
10. Have someone (asettle) review your PR quickly to ensure there are no breaks.
    Once that is complete, move to the next steps.

## Building release notes

To build the release notes, ensure your local copy is up to date:

`$ git pull origin master`

Run the following tox command:

`$ tox -e releasenotes`
