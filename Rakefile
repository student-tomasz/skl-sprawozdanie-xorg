document_name = "ato-1"
task :default => [:see]

task :see => ["#{document_name}.pdf"] do
  sh "xpdf #{document_name}.pdf &"
end

file "#{document_name}.pdf" => ["#{document_name}.tex"] do
  sh "pdflatex #{document_name}.tex"
  sh "pdflatex #{document_name}.tex"
  sh "pdflatex #{document_name}.tex"
end

task :clean do
  puts "cleaning"
  %x{rm *log *toc *aux *out}
end
