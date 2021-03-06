require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "orangewire_sender"
    gem.summary = %Q{Sends messages to The Orangewire}
    gem.description = %Q{Sends messages to The Orangewire}
    gem.email = "josh@stringbot.com"
    gem.homepage = "http://github.com/stringbot/orangewire_sender"
    gem.authors = ["Joshua Davison"]
    gem.add_dependency "rest-client", ">= 0"
    gem.add_development_dependency "riot", ">= 0.10.13"
    gem.add_development_dependency "rr", ">= 0.10.10"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
namespace :test do
  Rake::TestTask.new(:unit) do |test|
    test.libs << 'lib' << 'test'
    test.pattern = 'test/unit/test_*.rb'
    test.verbose = true
  end

  Rake::TestTask.new(:integration) do |test|
    test.libs << 'libs' << 'test'
    test.pattern = 'test/integration/test_*.rb'
    test.verbose = true
  end
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => 'test:unit'

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "orangewire_sender #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
