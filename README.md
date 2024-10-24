# Create or Update Comment GitHub Action
## Action Inputs

| Name              | Description                                                                                                       | Default         |
|-------------------|-------------------------------------------------------------------------------------------------------------------|------------------|
| `token`           | `GITHUB_TOKEN` (`issues: write`, `pull-requests: write`) or a `repo` scoped [PAT](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). | `GITHUB_TOKEN`   |
| `repository`      | The full name of the repository in which to create or update a comment.                                          | Current repository |
| `issue-number`    | The number of the issue or pull request in which to create a comment.                                           |                  |
| `comment-id`      | The id of the comment to update.                                                                                 |                  |
| `body`            | The comment body. Cannot be used in conjunction with `body-path`.                                               |                  |
| `body-path`       | The path to a file containing the comment body. Cannot be used in conjunction with `body`.                       |                  |
| `edit-mode`       | The mode when updating a comment, `replace` or `append`.                                                        | `append`         |
| `append-separator`| The separator to use when appending to an existing comment. (`newline`, `space`, `none`)                          | `newline`        |
| `reactions`       | A comma or newline separated list of reactions to add to the comment. (`+1`, `-1`, `laugh`, `confused`, `heart`, `hooray`) |                  |

## Create or Update Comment
[![CI](https://github.com/peter-evans/create-or-update-comment/workflows/CI/badge.svg)](https://github.com/peter-evans/create-or-update-comment/actions?query=workflow%3ACI)
[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Create%20or%20Update%20Comment-blue.svg?colorA=24292e&colorB=0366d6&style=flat&longCache=true&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAAM6wAADOsB5dZE0gAAABl0RVh0U29mdHdhcmUAd3d3Lmlua3NjYXBlLm9yZ5vuPBoAAAERSURBVCiRhZG/SsMxFEZPfsVJ61jbxaF0cRQRcRJ9hlYn30IHN/+9iquDCOIsblIrOjqKgy5aKoJQj4O3EEtbPwhJbr6Te28CmdSKeqzeqr0YbfVIrTBKakvtOl5dtTkK+v4HfA9PEyBFCY9AGVgCBLaBp1jPAyfAJ/AAdIEG0dNAiyP7+K1qIfMdonZic6+WJoBJvQlvuwDqcXadUuqPA1NKAlexbRTAIMvMOCjTbMwl1LtI/6KWJ5Q6rT6Ht1MA58AX8Apcqqt5r2qhrgAXQC3CZ6i1+KMd9TRu3MvA3aH/fFPnBodb6oe6HM8+lYHrGdRXW8M9bMZtPXUji69lmf5Cmamq7quNLFZXD9Rq7v0Bpc1o/tp0fisAAAAASUVORK5CYII=)](https://github.com/marketplace/actions/create-or-update-comment)

A GitHub action to create or update an issue or pull request comment.

## Usage

### Add a comment to an issue or pull request

```yaml
      - name: Create comment
        uses: peter-evans/create-or-update-comment@v4
        with:
          issue-number: 1
          body: |
            This is a multi-line test comment
            - With GitHub **Markdown** :sparkles:
            - Created by [create-or-update-comment][1]

            [1]: https://github.com/peter-evans/create-or-update-comment
          reactions: '+1'  

