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


5. Start the server

hugo server -D -log --baseURL "http://knetsolutions.in/" --bind "10.0.1.3" -p 80
