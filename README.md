#John's dotfiles
Modification of [Peter's dotfiles](https://github.com/piotrgiedziun/dotfiles) which works on ubuntu.<br>
This is a collection of dotfiles customised for my own usage.<br>
Based on [Roderik's dotfiles](https://github.com/roderik/dotfiles) and [Matt's dotfiles](https://github.com/mattbanks/dotfiles)

##Feature

###Navigation 
<table width="100%">
  <tr>
    <th>Alias</th><th>Method</th><th>Description</th>
  </tr><tr>
		<td> ..</td><td>cd ..</td><td> cd up</td>
	 </tr><tr>
		<td> ...</td><td>cd ../..</td><td> cd 2 x up</td>
	 </tr><tr>
		<td> ~</td><td>cd ~</td><td> cd to home directory</td>
	 </tr><tr>
		<td> cdh</td><td>cd ~</td><td>cd to home directory </td>
	 </tr><tr>
		<td> -</td><td>cd -</td><td> cd to previously visted folder</td>
	 </tr><tr>
		<td> cdd</td><td>cd ~/Downloads</td><td> </td>
	 </tr><tr>
		<td> cdp</td><td>cd ~/Projects</td><td> </td>
	 </tr><tr>
		<td> cdw</td><td>cd ~/Work</td><td> </td>
	 </tr>
</table>
###Installing package
<table width="100%">
  <tr>
   <th>Alias</th><th>Method</th><th>Description</th>
  </tr><tr>
	<td> apt</td><td>sudo apt-get install</td><td> </td>
	 </tr>
</table>
###Listing
<table width="100%">
  <tr>
    <th>Alias</th><th>Method</th><th>Description</th>
  </tr>
	 <tr>
		<td> ll</td><td>ls -l</td><td> </td>
	 </tr><tr>
		<td> la</td><td>ls -la</td><td> </td>
	 </tr><tr>
		<td> lsd</td><td>ls -l | grep "^d"</td><td> </td>
	 </tr>
</table>
###Network
<table width="100%">
  <tr>
   <th>Alias</th><th>Method</th><th>Description</th>
  </tr>
	<tr>
		<td> server</td><td>function</td><td>host python SimpleHTTPServer in current directory. Port might be given as parm (port)</td>
	 </tr><tr>
		<td> ip</td><td>dig +short myip.opendns.com @resolver1.opendns.com</td><td>return ip </td>
	 </tr><tr>
		<td> localip</td><td>ipconfig getifaddr en1</td><td> return local ip</td>
	 </tr><tr>
		<td> whois</td><td>whois -h whois-servers.net</td><td> </td>
	 </tr><tr>
		<td> flush</td><td>dscacheutil -flushcache && killall -HUP mDNSResponder</td><td>flush DNS </td>
	 </tr><tr>
		<td> sniff</td><td>sudo ngrep -d 'en1' -t '^(GET|POST) ' 'tcp and port 80'</td><td>sniff HTTP </td>
	 </tr><tr>
		<td> httpdump</td><td>sudo tcpdump -i en1 -n -s 0 -w - | grep -a -o -E \"Host\: .*|GET \/.*\"</td><td> </td>
	 </tr>
	 <tr>
		<td> json</td><td>function</td><td>Syntax-highlight JSON strings or files</td>
	 </tr><tr>
		<td> GET|POST|PUT|DELETE [url]</td><td>lwp-request -m '[METHOD]'</td><td> send GET/POST/PUT/DELETE request</td>
	 </tr>
</table>
###Others
<table width="100%">
  <tr>
    <th>Alias</th><th>Usage</th><th>Description</th>
  </tr>
	<tr>
		<td> killp</td><td>killp 8080</td><td>kill all processes working on port 8080</td>
	</tr>
	<tr>
		<td> mkd</td><td>mkd iLikePizza</td><td>make dir and cd to it</td>
	</tr>
	<tr>
		<td> copy</td><td>copy cat ~/.ssh/id_rsa.pub</td><td>copy given content to clipboard</td>
	 </tr><tr>
		<td> dataurl</td><td>dataurl image.png</td><td>return base64 of given object</td>
	 </tr>
	  <tr>
		<td> update</td><td>update</td><td>update gem, brew, system etc.</td>
	 </tr><tr>
		<td> lscleanup</td><td>lscleanup</td><td> clean up given dir</td>
	 </tr><tr>
		<td> cleanup</td><td>cleanup</td><td>clean up current dir</td>
	 </tr><tr>
		<td> emptytrash</td><td>emptytrash</td><td> clean trash</td>
	 </tr><tr>
		<td> urlencode</td><td>urlencode http://google.com</td><td> encode given url</td>
	 </tr><tr>
		<td> mergepdf</td><td>mergepdf --output out.pdf file1.pdf file2.pdf</td><td> merge PDF files</td>
	 </tr><tr>
		<td> beep</td><td>sleep 2 && beep</td><td> notify task is done</td>
	 </tr><tr>
		<td> extract</td><td>extract file.zip</td><td> extract given file</td>
	 </tr><tr>
		<td> roll</td><td>roll file.zip file.png file.jpg</td><td> create zip/tar/tar.gz archive from listed files</td>
	 </tr><tr>
		<td> please</td><td><p>$ powertop</p> 
				    <p>PowerTOP v2.5 must be run with root privileges.</p>
				    <p>$ please</p> </td><td> run last command with sudo permissions</td>
	 </tr>
</table>

##Directory structure
* **~/Projects** - own projects main dir
* **~/Work** - work projects main dir

##Virtualenv
* virtualenv directory `~/.virtualenvs`
* create new virtual env - `mkvirtualenv [env_name]`
* remove existing one - `rmvirtualenv [env_name]`
* workon existing one - `workon [env_name]`


##SSH
In order to have auto-complete option you have to add all yours hosts into `.ssh/config` file.

Example `.ssh/config` file:
```bash
Host github
	HostName github.com
	User janromaniak
	IdentityFile ~/.ssh/id_rsa

Host example.com
	User johniak
	IdentityFile ~/.ssh/johniak_rsa
```

##Installation
Open terminal and type
```bash
git clone https://github.com/johniak/dotfiles.git && cd dotfiles && ./install
```


