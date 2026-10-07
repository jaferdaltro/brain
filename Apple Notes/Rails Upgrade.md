---
apple-notes-id: 7E73C5C5-DCC6-4962-9F8B-34BD530DA71F
---
**Below is a summary of the changes applied to the code to successfully upgrade Rails to version 7.1.3.2.**
- gem ‘database_cleaner’ changed
	- https://github.com/DatabaseCleaner/database_cleaner
- app/controllers/api/v2/upload_statuses_controller.rb
	- https://blog.saeloun.com/2022/02/08/rails-7-raise-unsafe-redirect-error/
- app/services/fa_ticket_creator.rb
	- https://stackoverflow.com/questions/74430650/rails-7-activerecordassociationspreloader-new-preload
- lib/task/data_migration/recalculate_photos_timestamps.rb
	- processed? não existe mais
- config/environments/development.rb / config/environments/production.rb / config/environments/staging.rb / config/environments/test.rb / config/environments/uat.rb
	- Changed from: config.cache_classes = false
	- Changes to: config.enable_reloading = true
	- https://guides.rubyonrails.org/configuring.html#config-cache-classes
- config/initializers/new_framework_defaults.rb
	- this was a compatibility layer for versions previous of ruby 2.4 to ensure the behavior of to_time to preserve the timezone when converting to an instance of Time instead of the previous behavior of converting to the local system timezone. But the to_time conversions we had were unnecessaries and so removed together with this config: https://www.bigbinary.com/blog/to-time-preserves-time-zone-info-in-ruby-2-4
- spec/factories/project_membership.rb / spec/lib/task/query_spec.rb
	- Unnecessary to_time conversion
- spec/rails_helper.rb
	- config.fixture_path was changed to config.fixture_path to allow multiple fixture paths
		- https://rubyonrails.org/2023/3/18/this-week-in-rails-testfixtures-fixture_path-deprecation-findermethods-find-support-for-composite-primary-key-values-87e6e69a
The other changes that were necessary were made to maintain the functioning of the new autoloader used, zeitwerk mode.