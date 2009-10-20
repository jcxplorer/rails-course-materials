begin
  require 'slidedown'
rescue LoadError
end


task :default => ["slides"]

desc "Generate HTML for all slides"
task :slides do
  slides = FileList['slides/*.textile']
  
  `scarlet -g slides`
  
  slides.each do |slide|
    print slide
    status = system "scarlet '#{slide}' > '#{slide.chomp('.textile')}.html'"
    puts status ? "\t\tdone" : "\t\tFAILED!"
  end
end