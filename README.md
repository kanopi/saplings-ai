![saplings](https://github.com/kanopi/saplings/assets/5177009/a6377e32-deb2-49d8-873a-f3dd5a36fa7c)

# Saplings - AI

Helpful AI functionality for content creators.

## Features

### Summary from OpenAI - Post

This ECA workflow uses chatGPT to write a summary of the article and save it to
the Description field on save if the field does not have one. If the Description
has any content at all, the workflow is not run.

OpenAI APIs have costs associated with them. [Pricing](https://openai.com/api/pricing/)

## Roadmap

* Summary from OpenAI - Page Workflow
* Summary from OpenAI - Event Workflow
* Featured Image from OpenAI (DALL-E) Workflow
* Text to Audio Workflow
* Audio to Text Workflow
* CKEditor integration(s)

## Installation

```
composer require kanopi/saplings-ai
cd web && php core/scripts/drupal recipe ../recipes/saplings-ai
```

There are a couple of patches that are needed momentarily.

Add the following to your project's composer.json

```
"patches": {
    "drupal/openai": {
        "Return type declaration error": "https://www.drupal.org/files/issues/2024-06-28/openai-OpenAIActionBase_return_type-3450196-6.patch",
        "Misspelled property triggers errors in ECA module": "https://git.drupalcode.org/project/openai/-/merge_requests/92.diff"
    }
}
```

Then run `composer update drupal/openai`

### Configure OpenAI

Create an account and an User API key at https://platform.openai.com

Add the OpenAI User key and organization ID to: `/admin/config/openai/settings`

Save an you are ready to start AI-ing!
