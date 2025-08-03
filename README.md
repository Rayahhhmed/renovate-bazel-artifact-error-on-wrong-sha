# 37143

## Current behavior

Currently, when Renovate tries to update bazel http_archive rule and fails to find artifact sha, it will silently raise the PR in a broken state. This Reproduction shows how the `strip_prefix`, `sha` is not updated at all and most importantly the `url` is in an invalid state. 

## Expected behavior

It should throw an artifact error to let the user know that the current dependency needs to be looked into and let them know that the hash could not be calculated. 

A bit more detail: Often times network firewall rules may block certain urls from being accessed, hence throwing an artifact error will let users dissect the cause of issue quicker and prevent automerging from merging in dependencies in a broken state.

## Link to the Renovate issue or Discussion

This reproduction shows the bug for (this disccusion)[https://github.com/renovatebot/renovate/discussions/37143].
A PR is raised to address this (here)[https://github.com/renovatebot/renovate/pull/37249].
