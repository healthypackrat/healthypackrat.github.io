require 'erb'

require 'bundler/setup'

require 'redcarpet'

task default: 'index.html'

task 'index.html' do |t|
  markdown = Redcarpet::Markdown.new(Redcarpet::Render::HTML)
  body = markdown.render(File.read(t.name.ext('md')))
  html = ERB.new(File.read('layout.erb')).result(binding)
  File.write(t.name, html)
end
