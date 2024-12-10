# Personal blog site - static HTML exported from Drupal

## Aims

- Share solutions to problems I've found that I rarely see
- Immerse myself in Drupal again
- Create a low-impact site - there's no need to have a dynamic site for this
- Create a low-maintenance site
- Update my frontend skills

## Static generation

Run this from the root directory:

```
./scripts/generate-static-site
```

`settings.local.php` turns on Twig debugging, which we don't want in the static site. I've added a check to prevent `settings.local.php` from being loaded during static generation, but if [Tome only exports pages that have changed i.e. what's cached](https://www.drupal.org/project/tome/issues/3023453#comment-12917230). 

The script also lists the files in the static directory after generation so we can check it's worked.

### Development note

My approach to static generation will not scale well. If there were many pages then we would be unnecessarily regenerating pages that have not changed. My use-case here may be unusual, as the site is constantly in development, and being worked on by the developer and content editor who are the same person.