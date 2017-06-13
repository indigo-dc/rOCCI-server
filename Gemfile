source 'https://rubygems.org'

git_source(:github) do |repo_name|
  repo_name = "#{repo_name}/#{repo_name}" unless repo_name.include?("/")
  "https://github.com/#{repo_name}.git"
end

gem 'rails', '~> 5.1.1'
gem 'puma', '~> 3.7'
gem 'rack-cors', '~> 0.4'
gem 'logstasher', '~> 1.2'

gem 'occi-core', '= 5.0.0.beta.2', require: 'occi/infrastructure-ext' # '~> 5.0.0'

group :development, :test do
  gem 'byebug'
  gem 'listen', '>= 3.0.5', '< 3.2'
  gem 'spring'
  gem 'spring-watcher-listen', '~> 2.0.0'
end

# Include external bundles
path = File.join(File.dirname(__FILE__), 'lib', 'backends', 'bundles')
if File.directory?(path)
  Dir.glob(File.join(path, "Gemfile.*")) do |gemfile|
      eval(IO.read(gemfile), binding)
  end
end
