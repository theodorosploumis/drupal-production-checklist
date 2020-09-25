# Drupal production checklist

An example of a simplified checklist for a Drupal website launch.
Current example includes migration tasks from a 7.x website to 9.x.
The steps bellow are not mandatory and their order is not strict.

## Checklist

- [ ] Other: Define the datetime for the launch to happen.
- [ ] GDPR: Remove IP tracking on Webforms
- [ ] GDPR: Remove IP tracking on dblog
- [ ] GDPR: Add cookies banner
- [ ] Drupal: Remove old Super Admin users
- [ ] Drupal: Remove demo Nodes and content
- [ ] Merge git branch stage to master (Pull Request)
- [ ] Git pull && composer install - [ ] - [ ] no- [ ] dev && drush cim - [ ] y && drush updb
- [ ] Drupal: Content freeze (usually on stage website)
- [ ] Server: Copy public files from 7.x
- [ ] Server: Copy db from Stage to Prod (except if there is no new content on stage)
- [ ] Drupal: Execute final migrations (from the frozen production 7.x db)
- [ ] Server: Fix permissions for translations folder and update translations
- [ ] Drupal: Test all forms to send emails (if set to)
- [ ] Drupal: Disable all migration related modules.
  - [ ] custom_migrate_\* (current site custom migrations)
  - [ ] migrate_plus
  - [ ] migrate_tools
  - [ ] migrate_upgrade
  - [ ] migrate_drupal
  - [ ] migrate_ui
  - [ ] migrate
- [ ] Drupal: Disable display errors on screen
- [ ] Drupal: Disable modules used on development except if they are needed.
  - [ ] devel
  - [ ] kint
  - [ ] vardumper
  - [ ] email_reroute
  - [ ] stage_file_proxy
  - [ ] shield
  - [ ] views_ui
  - [ ] field_ui
  - [ ] webform_ui
- [ ] Drupal: Enable Caching modules and set performance.
  - [ ] page_cache (core)
  - [ ] dynamic_page_cache (core)
  - [ ] big_pipe (core)
  - [ ] advagg
  - [ ] http_cache_control
  - [ ] quicklink
  - [ ] http_override_headers
  - [ ] lazy
  - [ ] minifyhtml
  - [ ] critical_css
- [ ] Drupal: Enable dblog and check for mass php errors, 404 errors etc
- [ ] Drupal: Set private folder (if need to)
- [ ] Drupal: Fix settings.php warnings
  - [ ] trusted host patterns
  - [ ] simplei (drupal module settings)
  - [ ] private files
- [ ] Server: Add cron jobs
- [ ] Server: Change DNS
- [ ] Drupal: Run cron several times to index on Search
- [ ] Drupal: Rebuild content permissions
- [ ] Drupal: Update project translations `/admin/reports/translations/check`
- [ ] Drupal: Download a complete whole archive of the new website (code, database, public files)
- [ ] Server: Move old 7.x site to a protected new subdomain
- [ ] Other: Update LastPass passwords and links
- [ ] Other: Update site Docs and internal company Docs
- [ ] Other: Generate internal report for company. Examples.
  - [ ] Google page speed results (compared to the old website)
  - [ ] new/interesting drupal modules used
  - [ ] issues we solved
  - [ ] patches applied
  - [ ] tasks time estimations that were wrong
  - [ ] findings about Drupal or other used services
- [ ] Other: Write possible Blog posts about the project


## Resources

- https://www.drupal.org/project/production_checklist

