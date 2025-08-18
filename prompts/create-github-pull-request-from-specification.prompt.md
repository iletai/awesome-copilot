---
mode: 'agent'
description: 'Create GitHub Pull Request for feature request from specification file using pull_request_template.md template.'
tools: ['codebase', 'search', 'github', 'get_pull_request', 'create_pull_request', 'update_pull_request', 'get_pull_request_diff']
---
# Create GitHub Pull Request from Specification

Create GitHub Issue for the specification at `${workspaceFolder}/.github/pull_request_template.md` .

## Process

1. Analyze specification file template from '${workspaceFolder}/.github/pull_request_template.md' to extract requirements by 'search' tool.
2. Create Pull request draft template by using 'create_pull_request' tool on to `${input:targetBranch}`. and make sure don't have any pull request of current branch was exist `get_pull_request`. If has continue to step 4, and skip step 3.
3. Get change in pull request draft was created by using 'get_pull_request_diff' tool. To anaylytic infomation was change in Pull Request draft was create before.
4. Update Pull Request body was created in previous step by 'update_pull_request' tool. To update infomation exist to body, title with template using pull_request_template.md was get in first step.
5. Switch from draft to ready for review by using 'update_pull_request' tool. To update state of pull request.
6. Response URL Pull request was create to user.

## Requirements
- Single issue for the complete specification
- Clear title/pull_request_template.md identifying the specification
- Fill enought infomation onto pull_request_template.md
- Verify against existing issues before creation
- Don't ask user for permission between each step. Continue til the end.


