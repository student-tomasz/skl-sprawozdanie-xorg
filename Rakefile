$lc = "xelatex"
$lf = "-interaction=nonstopmode"

$exec = "sprawozdanie-xorg.pdf"
$objs = %w{*.out *.log *.aux *.pdf *.toc}

rule '.pdf' => '.tex' do |t|
  2.times do
    sh "#{$lc} #{$lf} #{t.source}"
  end
end

task :default => :build

task :build => $exec

task :show => $exec do
  os = if RUBY_PLATFORM.include? 'darwin' then :mac else :linux end
  case os
  when :mac
    sh "open #{$exec}"
  else
    sh "xpdf #{$exec} &"
  end
end

task :clean do
  $objs.each { |file| sh "rm -f #{file}" }
end
