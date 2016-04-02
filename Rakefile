task :default => :new

require 'fileutils'

desc "创建新 post"
task :new do
  puts "请输入要创建的 post URL："
    @url = STDIN.gets.chomp
    puts "请输入 post 标题："
    @name = STDIN.gets.chomp
    puts "请输入 post 标签："
    @tag = STDIN.gets.chomp
    @slug = "#{@url}"
    @slug = @slug.downcase.strip.gsub(' ', '-')
    @date = Time.now.strftime("%F")
    @post_name = "_posts/#{@date}-#{@slug}.md"
    if File.exist?(@post_name)
            abort("文件名已经存在！创建失败")
    end
    FileUtils.touch(@post_name)
    open(@post_name, 'a') do |file|
            file.puts "---"
            file.puts "layout: post"
            file.puts "title: #{@name}"
            file.puts "author: BadReese"
            file.puts "date: #{Time.now}"
            file.puts "categories: blogs"
            file.puts "tag: #{@tag}"
            file.puts "---"
    end
end