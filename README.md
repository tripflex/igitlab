	iii   GGGG  iii tt    LL              bb      
	     GG  GG     tt    LL        aa aa bb      
	iii GG      iii tttt  LL       aa aaa bbbbbb  
	iii GG   GG iii tt    LL      aa  aaa bb   bb 
	iii  GGGGGG iii  tttt LLLLLLL  aaa aa bbbbbb  
	                                              
# iGitLab - GitLab Ubuntu/Debian Installer Bash/Shell Script

Name says it all, use this script to install GitLab on any debian flavored server, check the script for configuration options.

Tested working on 5-4-stable, but should work on other versions and master as well.

## Installation
``` bash
wget https://raw.github.com/tripflex/igitlab/master/igitlab
chmod +x igitlab
```

## Usage
``` bash
./igitlab mygitdomain.com
```

## Configuration Options

### GitLab Release
Set this to whatever branch you want to use for the GitLab installation.  Current tested working version is 5-4-stable, change to master for latest.
``` bash
gitlab_release=5-4-stable
```

### Unicorn or Puma
Version 5.1 through 5.9 uses Puma, whereas 6.0 will start using Unicorn again.  Set this to 1 if you are installing a version that requires Unicorn instead of Puma.
``` bash
useunicorn=0
```

### Ruby Download URL
Set this to the URL to download Ruby source
``` bash
rubydlurl="http://ftp.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p392.tar.gz"
```

### MySQL Root Password
Set this to the root password for MySQL access.  If MySQL is not setup yet on the server you will be prompted to set one up, and then enter it again for the script to use.  You will probably only need to set this if you already have MySQL setup, or just enter it when script asks for it.
``` bash
mysqlpasswd=""
```

### Apt Arguments
Set this to the arguments you want ran with apt when updating, and installing.  Current default is set to "-qq" which assumes -y and supresses output from apt.  Set to -y for standard output.
``` bash
# -s = simulate
# -y = yes (no prompt)
# -q = quiet
# -qq = even more quiet (also implies -y, do not use with -s)
aptget_arguments="-qq"
```

### Apt Log Files
Set these to filenames you want to use for apt logs
``` bash
APTLOG=apt.log
APTERRLOG=apterror.log
```