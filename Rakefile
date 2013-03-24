# -*- mode: ruby; coding: utf-8 -*-
require 'rubygems'
require './lib/opencv/psyched_yaml'
require 'hoe'
require 'rake/extensiontask'

Hoe.plugin :gemspec

hoespec = Hoe.spec 'ruby-opencv' do |s|
  s.summary = 'OpenCV wrapper for Ruby'
  s.description = 'ruby-opencv is a wrapper of OpenCV for Ruby. It helps you to write computer vision programs (e.g. detecting faces from pictures) with Ruby.'
  s.licenses = ['The BSD License']
  s.developer('lsxi', 'masakazu.yonekura@gmail.com')
  s.developer('ser1zw', 'azariahsawtikes@gmail.com')
  s.developer('pcting', 'pcting@gmail.com')

  s.readme_file  = 'README.md'
  s.history_file = 'History.txt'
  s.spec_extras = { :extensions => ['ext/opencv/extconf.rb'] }
  s.test_globs = ['test/test_*.rb']
  s.urls = ['https://github.com/ruby-opencv/ruby-opencv/']

  s.extra_dev_deps << ['rake-compiler', '>= 0'] << ['hoe-gemspec']

  Rake::ExtensionTask.new('opencv', spec) do |ext|
    ext.lib_dir = File.join('lib', 'opencv')
  end
end

hoespec.spec.files.delete('.gemtest')

Rake::Task[:test].prerequisites << :compile

# vim: syntax=ruby
