require 'middleman-gh-pages'
require 'open-uri'

task :default => [:fetch, :build]

APP_NAMES = %w(
  people
  services
  check-ins
  registrations
)

task :fetch do
  base_url = case ENV['DEPLOY_ENV']
  when 'development'
    'http://api.pco.dev'
  when 'staging'
    'https://api-staging.planningcenteronline.com'
  else
    'https://api.planningcenteronline.com'
  end
  APP_NAMES.each do |app|
    url = "#{base_url}/#{app}/v2/docs"
    puts "getting #{url}..."
    content = open(url, 'Accept' => 'text/html').read
    path = "source/includes/_#{app}.md"
    File.open(File.expand_path("../#{path}", __FILE__), 'w') do |file|
      file.write(content)
    end
    puts "  wrote #{path}"
  end
end
