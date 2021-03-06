![.github/workflows/comment-pr.yml](https://github.com/mb2dev/github-action-comment-pull-request/workflows/.github/workflows/comment-pr.yml/badge.svg?branch=test%2Ftest-comment-on-pull-request)

# Github Action - Comment Pull request

This github action comments an opened PR with a given message. You can also put some reactions to the comment.

## Inputs
 - message : The message you want to display inside the comment.
 - github token: The `GITHUB_TOKEN` secret. You can use the default `${{ secret.GITHUB_TOKEN }}` to tag the message with the github-actions bot .
 - reactions: A list of reactions separated by `|` 
      - reaction suported : +1 | -1 | laugh | hooray | confused | heart | rocket | eyes


## Example usage

````
on: [pull_request]

jobs:
    build:
        name: Comment a pull_request
        runs-on: ubuntu-latest
        steps:
            - name: Checkout
              uses: actions/checkout@v2

            - name: Comment a pull_request
              uses: mb2dev/github-action-comment-pull-request@1.0.0
              with:
                message: "Hello, It's my first comment with Github action !"
                GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
                reactions: "+1 | -1 | laugh | hooray | confused | heart | rocket | eyes"
````

See example in [opened PR](https://github.com/mb2dev/github-action-comment-pull-request/pull/3)

# Build

To build the project, you must run the cmd :
````
$ npm run build
````
The build transpile the typescript `src/main.ts` into the `lib/main.js` that is used inside the Docker container.
