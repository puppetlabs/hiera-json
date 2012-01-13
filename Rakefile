require 'rubygems'
require 'rubygems/package_task'
require 'rspec/core/rake_task'
require 'tasks/release'

spec = Gem::Specification.new do |s|
  s.name = "hiera-json"
  s.version = described_version
  s.author = "Puppet Labs"
  s.email = "info@puppetlabs.com"
  s.homepage = "https://github.com/puppetlabs/hiera-json/"
  s.summary = "JSON backend for the Hiera hierarcical data store"
  s.description = "Store Hiera data in JSON"
  s.files = FileList["lib/**/*"].to_a
  s.require_path = "lib"
  s.test_files = FileList["spec/**/*.rb"].to_a
  s.has_rdoc = true
  s.add_dependency 'hiera', '~>0.3.0'
  s.add_dependency 'json'
end

Gem::PackageTask.new(spec) do  |pkg|
  pkg.need_tar = true
end

desc "Run all specs"
RSpec::Core::RakeTask.new(:test) do |t|
    t.pattern = 'spec/**/*_spec.rb'
    t.rspec_opts = File.read("spec/spec.opts").chomp || ""
end

task :default => [:test, :repackage]
