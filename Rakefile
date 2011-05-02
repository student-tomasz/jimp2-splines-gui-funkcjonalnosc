$lc = "xelatex"
$lf = "-interaction=nonstopmode"

$exec = "specyfikacja-funkcjonalna.pdf"

rule '.pdf' => '.tex' do |t|
  for i in 1..2 do
    sh "#{$lc} #{$lf} #{t.source} >> /dev/null"
  end
end

task :default => :build

task :build => $exec do
end

task :show => $exec do
  sh "open #{$exec}" rescue nil
end

task :clean do
  %w{*.out *.log *.aux *.pdf}.each do |f|
    sh "rm #{f}" rescue nil
  end
end
