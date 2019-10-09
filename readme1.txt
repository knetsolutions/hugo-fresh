Development
============
1. Dowload hugo extended version v0.55.6 as below

    wget  https://github.com/gohugoio/hugo/releases/download/v0.55.6/hugo_extended_0.55.6_Linux-64bit.tar.gz

2. unzip and move it to /usr/bin folder

3. create new site(knetsolutions)
   hugo new site knetsolutions

4. 
cd knetsolutions
git clone https://github.com/knetsolutions/hugo-fresh themes/hugo-fresh
rm config.toml
cp themes/hugo-fresh/exampleSite/config.yaml .
cp themes/hugo-fresh/exampleSite/content/* content/. -rf
cp themes/hugo-fresh/static/mininet static/. -rf


5. Start the server

hugo server -D -log --baseURL "http://knetsolutions.in/" --bind "10.0.1.3" -p 80


6. Generate html file

hugo

it will generate the html files in public folder. 

cp public themes/hugo-fresh/. -rf


Deploy this public folder in apache webserver to serve the webserver.




