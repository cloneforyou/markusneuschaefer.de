require "rake/contrib/ftptools"


task :default do
    sh("JEKYLL_ENV=production bundle exec jekyll build")
end

Dir.chdir('_site') do
    Rake::FtpUploader.connect('/htdocs/', ENV['FTP_HOST'], ENV['FTP_USER'], ENV['FTP_PASS']) do |ftp|
        ftp.verbose = true
        ftp.upload_files("./**/*")
    end
end
