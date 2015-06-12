require 'opal'
require 'opal/browser'

desc "Compile Ruby to JS"
task :build do
  builder = Opal::Builder.new
  builder.processed.map { |asset| [asset.filename, asset.to_s] }

  Opal.append_path "app"

  File.open("conway.js", "w") do |js_file|
    js_file.write Opal::Builder.build("conway").to_s
  end
end

desc "Test Algorithm"
task :test do
  puts `ruby './test/conway/algorithm.rb'`
end

task :default => :build