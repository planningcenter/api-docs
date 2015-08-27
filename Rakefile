require 'middleman-gh-pages'
require 'open-uri'

task :default => [:fetch, :build]

task :fetch do
  base_url = case ENV['DEPLOY_ENV']
  when 'development'
    'http://api.pco.dev'
  when 'staging'
    'https://api-staging.planningcenteronline.com'
  else
    'https://api.planningcenteronline.com'
  end
  %w(
    people
    services
  ).each do |app|
    url = "#{base_url}/#{app}/v2/docs"
    p "getting #{url}..."
    content = open(url).read
    path = "source/includes/_#{app}.md"
    File.open(File.expand_path("../#{path}", __FILE__), 'w') do |file|
      file.write(content)
    end
    puts "  wrote #{path}"
  end
end
