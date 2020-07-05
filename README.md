[1]: http://gitbook.zhangjikai.com/bookjson.html
[2]: /images/create_a_new_repository.png
[3]: /images/github_pages_settings.png
[4]: https://github.com/marketplace/travis-ci
[5]: /images/travis_ci_repositories.png
[6]: https://github.com/settings/tokens
[7]: /images/github_presonal_access_tokens.png
[8]: /images/github_presonal_access_tokens_scopes.png
[9]: /images/Travis_CI_Token.png

# Gitbook Template

[![Build Status](https://travis-ci.com/renkeju/gitbook-template.svg?branch=master)](https://travis-ci.com/renkeju/gitbook-template)

## Project Structure

1. Clone the template and remove the history in the template

    ```
    git clone https://github.com/renkeju/gitbook-template l2tp-usage-guide
    cd l2tp-usage-guide && rm -rf .git
    ```

2. Modify the template

    * `.travis.yml`

        * recipients: change to your personal email address
        * REF: Change to your github project address

    * `book.json`

        To modify the corresponding configuration of gitbook, you can refer to this document [book.json configuration file][1]

    * `SUMMARY.md`
        
        Define the directory structure

    * `CNAME`

        If you do not need to specify the domain name you use, you can delete this file.
        
        If necessary, please use the CNAME method in the DNS service provider to point gitbook.renkeju.com to renkeju.github.com

3. Create a new project on github

    For example, I named the new warehouse l2tp-usage-guide

    ![Create a new warehouse][2]

    Push the modified template to the new warehouse

    ```
    echo "# l2tp-usage-guide"> README.md
    git init
    git add.
    git commit -m "first commit"
    git remote add origin git@github.com:renkeju/l2tp-usage-guide.git
    git push -u origin master
    ```
    
## Github Pages

1. Create a new gh-pages branch:

    ```
    git checkout -b gh-pages
    git push origin gh-pages
    ```

2. Open the Github Pages service in the project `Settings` -> `GitHub Pages`:

   ![Github Pages Settings][3]

## Travis CI

1. [Click here][4] Start the Travis service for the project l2tp-usage-guide just created on github:

    ![Travis CI Warehouse][5]

2. Apply for token in [Personal Settings][6] to give Travis permission to modify this project:

    ![Github Personal Access Token Field][8]

    Then select repo and click the generate button:

    ![Github Personal Access Token][7]

3. Copy the generated token, fill in the Travis settings-global variables, and name it TOKEN:

    ![Travis CI TOKEN][9]
